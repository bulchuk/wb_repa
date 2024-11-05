#по ручке получаем json ответ аргументов записи по определенному запросу
#необходимо преобразовать в единую запись для проверки корректности

Вариант 1. 

import json

json_data = { --данные--
}

string_data = "|".join([json_data["Query"], json_data["NormQuery"], json_data["Miner"], json_data["MinerArgs"], ""]) + '|'
print(string_data)


Вариант 2. 

#входные данные JSON
json_data = {
   --данные--
}

#извлечение данных
query = json_data["Query"]
norm_query = json_data["NormQuery"]
miner_names = ";".join(factor["MinerName"] for factor in json_data["MinerArgs"]["Factors"])

#формирование строки аргументов с разделением пробелами внутри майнера
miner_args_list = []
for factor in json_data["MinerArgs"]["Factors"]:
    args = " ".join(f'--{arg["name"]}="{arg["value"]}"' for arg in factor["Args"])
    miner_args_list.append(args)

#объединение всего в финальный формат с разделением точкой с запятой
miner_args = ";".join(miner_args_list)
output = "|".join([query, norm_query, miner_names, miner_args, ""]) + '|'

print(output)
