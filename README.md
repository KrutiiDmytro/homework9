# homework9
# Заданиен 1
# Создайте словарь с количеством элементов не менее 5-ти.
# Поменяйте местами первый и последний элемент объекта.
# Удалите второй элемент. Добавьте в конец ключ «new_key» со значением «new_value».
# Выведите на печать итоговый словарь.
# Важно, чтобы словарь остался тем же (имел тот же адрес в памяти).
d = {'one': 1, 'two': 2, 'three': 3, 'four': 4,
     'five': 5, 'six': 6, 'new_key': 'new_value'}
del d['two']
d['one'] = d['six']
print(d)

# Заданиен 2
# Как получить значение по ключу "marks" словаря
# student = {"name": "Emma", "class": 9, "marks": 75}
student = {'name': 'Emma', 'class': 9, 'marks': 75}
print(student.get('marks'))

# Заданиен 3
# Что выведет этот код?
p = {'name': 'Mike', 'salary': 8000, 'age': 34}
print(p.get('age'))

# Заданиен 4
# Как получить "d":sample = {"1":["a","b"], "2":["c","d"]}.
sample = {'1': ['a', 'b'],
          '2': ['c', 'd']
          }
print(sample['2'][1])

# Заданиен 5
# Дан список стран и городов каждой страны. Затем дан смписок названия городов.
# Для каждого города укажите, в какой стране он находится.
country = ['Ukraine', 'Germany', 'Italy', 'France']
city = [('Kiyv', 'Odessa'), ('Berlin', 'Humburg'), 'Rome', 'Paris']
A = dict(zip(country, city))
print(A)

# Заданиен 6
# Для английского алфовита сгенерировать словарь-шифратор,
# то есть словарь, где ключ буква алфавита, а значение являются случайное значение.
# Используя словарь, зашифровать/расшифровать введенное сообщение.
crypt = {
    'a': 98, 'b': 99, 'c': 100, 'd': 101, 'e': 102, 'f': 103, 'g': 104,
    'h': 105, 'i': 106, 'j': 107, 'k': 108, 'l': 109, 'm': 110, 'n': 111,
    'o': 112, 'p': 113, 'q': 114, 'r': 115, 's': 116, 't': 117, 'u': 118,
    'v': 120, 'w': 121, 'x': 122, 'y': 124, 'z': 125
}

del_a = '-'
del_w = '&'
phrase = input('Какую фразу будем шифровать?: ')
code_phr = ''
for _p in phrase:
    code_phr += str(crypt.get(_p, '')) + (del_w if _p == ' ' else del_a)
print(code_phr)

decode_phr = ''
tmp_str = ''
for i in range(len(code_phr)):
    if code_phr[i] != del_a and code_phr[i] != del_w:
        tmp_str += code_phr[i]
    else:
        if code_phr[i] == del_a:
            for k, v in crypt.items():
                if tmp_str == str(v):
                    decode_phr += k
        else:
            decode_phr += ' '
        tmp_str = ''
print(phrase == decode_phr)
print(decode_phr)
