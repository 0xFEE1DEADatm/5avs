#include <Windows.h>
#include <iostream>
#include <fstream>


int findMaxSegment(int* arr, int k)
{
	int max = 0;
	for (int i = 0; i < k; i++)
	{
		if ((arr[i + 1] - arr[i]) > max)
			max = arr[i + 1] - arr[i];
	}
	return max;
}
void swap(int* a, int* b)
{
	int tmp = *a;
	*a = *b;
	*b = tmp;
}
void bubbleSort(int* arr, int k)
{
	bool swapped;
	while (k--)
	{
		swapped = false;
		for (int i = 0; i < k; i++)
		{
			if (arr[i] > arr[i + 1])
			{
				
				swap(&arr[i], &arr[i + 1]);
				swapped = true;
				
			}
		}
		if (swapped == false)
			break;
	}
}
bool cheking(int w, int h, int n)
{
	int min = 40000;
	if (w < 1 || h>40000)
	{
		std::cout << "Error! Check your enter requirement again.";
		return false;
	}
	else
	{
		if (w < h)
			min = w;
		else if (h < w)
			min = h;
		else
			min = h;

		if (n < 0 || n>min)
		{
			std::cout << "Error! Check your enter requirement again.";
			return false;
		}
	}
	return true;
}
int main()
{
	std::fstream file("input.txt");
	int w, h, n, x, y;

	if (file)
	{
		file >> w >> h >> n;
		int* abs = new int[n + 2];
		int* ord = new int[n + 2];
		
		if (cheking(w, h, n))
		{
			std::cout << "Mesh width: " << w << std::endl;
			std::cout << "Mesh high: " << h << std::endl;
			std::cout << "Number of tower: " << n << std::endl;
			std::cout << std::endl;

			abs[0] = 0;
			ord[0] = 0;
			abs[n + 1] = w + 1;
			ord[n + 1] = h + 1;

			for (int i = 1; i < n + 1; i++)
			{
				file >> x >> y;
				abs[i] = x;
				ord[i] = y;
			}

			bubbleSort(abs, n + 2);
			bubbleSort(ord, n + 2);

			int max_x = findMaxSegment(abs, n + 2);
			int max_y = findMaxSegment(ord, n + 2);

			std::cout << "Number of cells in the largest rectangle not protected by towers: " << (max_x - 1) * (max_y - 1);
		}

	}
	else std::cout << "File wasn`t opened.\n";
	return 0;
}
