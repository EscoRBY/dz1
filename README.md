# dz1
//Zadanie 1 Задайте двумерный массив. Напишите программу, которая упорядочит по убыванию элементы каждой строки двумерного массива.
int[,] arr = new int[,] {
    { 1, 4, 7, 2 },
    { 5, 9, 2, 3 },
    { 8, 4, 2, 4 }
};

for (int i = 0; i < arr.GetLength(0); i++) {
    for (int j = 0; j < arr.GetLength(1) - 1; j++) {
        for (int k = j + 1; k < arr.GetLength(1); k++) {
            if (arr[i, j] < arr[i, k]) {
                int temp = arr[i, j];
                arr[i, j] = arr[i, k];
                arr[i, k] = temp;
            }
        }
    }
}

for (int i = 0; i < arr.GetLength(0); i++) {
    for (int j = 0; j < arr.GetLength(1); j++) {
        Console.Write(arr[i, j] + " ");
    }
    Console.WriteLine();
}
//end
//Zadanie 2 Задайте прямоугольный двумерный массив. Напишите программу, которая будет находить строку с наименьшей суммой элементов.
int[,] arr = new int[,] {
    { 1, 4, 7, 2 },
    { 5, 9, 2, 3 },
    { 8, 4, 2, 4 },
    { 5, 2, 6, 7 }
};

int minSum = int.MaxValue;
int minIndex = -1;

for (int i = 0; i < arr.GetLength(0); i++) {
    int sum = 0;
    for (int j = 0; j < arr.GetLength(1); j++) {
        sum += arr[i, j];
    }
    if (sum < minSum) {
        minSum = sum;
        minIndex = i;
    }
}

Console.WriteLine("Строка с наименьшей суммой элементов: " + (minIndex + 1));
//end
//Zadanie 3  Задайте два двумерных массива (от 0 до 10). Напишите программу, которая будет находить произведение двух массивов (поэлементное).
int[,] arr1 = new int[,] {
    { 2, 4 },
    { 3, 2 }
};

int[,] arr2 = new int[,] {
    { 3, 4 },
    { 3, 3 }
};

int[,] result = new int[arr1.GetLength(0), arr1.GetLength(1)];

for (int i = 0; i < arr1.GetLength(0); i++) {
    for (int j = 0; j < arr1.GetLength(1); j++) {
        result[i, j] = arr1[i, j] * arr2[i, j];
    }
}

for (int i = 0; i < arr1.GetLength(0); i++) {
    for (int j = 0; j < arr1.GetLength(1); j++) {
        Console.Write(result[i, j] + " ");
    }
    Console.WriteLine();
}
//end
//Zadanie 4 Напишите программу, которая заполнит спирально массив 4 на 4.
int[,] arr = new int[4, 4];
int counter = 1;
int rowStart = 0;
int rowEnd = 3;
int colStart = 0;
int colEnd = 3;

while (counter <= 16) {
    for (int i = colStart; i <= colEnd; i++) {
        arr[rowStart, i] = counter;
        counter++;
    }
    rowStart++;

    for (int i = rowStart; i <= rowEnd; i++) {
        arr[i, colEnd] = counter;
        counter++;
    }
    colEnd--;

    for (int i = colEnd; i >= colStart; i--) {
        arr[rowEnd, i] = counter;
        counter++;
    }
    rowEnd--;

    for (int i = rowEnd; i >= rowStart; i--) {
        arr[i, colStart] = counter;
        counter++;
    }
    colStart++;
}

for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 4; j++) {
        Console.Write("{0:D2} ", arr[i, j]);
    }
    Console.WriteLine();
}
//end
