# Привет! 👋
def fib(n):
    if n <= 0:
        return "Неверный ввод. Введите число больше нуля."
    elif n == 1:
        return [0]
    elif n == 2:
        return [0, 1]
    else:
        fib_sequence = [0, 1]
        for i in range(2, n):
            fib_sequence.append(fib_sequence[i-1] + fib_sequence[i-2])
        return fib_sequence

n = int(input("Введите номер числа в последовательности Фибоначчи: "))
fib_sequence = fib(n)
print(fib_sequence)



def fib_generator(n):
    a, b = 0, 1
    count = 0
    while count < n:
        yield a
        a, b = b, a + b
        count += 1

n = int(input("Введите номер числа в последовательности Фибоначчи: "))
for num in fib_generator(n):
    print(num, end=" ")