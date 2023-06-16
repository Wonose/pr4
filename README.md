# beginner-html-site-styled
A simple one page website created to help complete beginners learn HTML basics, which in this repo has also been styled to help beginners learn CSS basics. The styling is explained over the course of [https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/CSS_basics](https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/CSS_basics).

[Run the example live](http://mdn.github.io/beginner-html-site-styled/).

#define _CRT_SECURE_NO_WARNINGS
#include <stdlib.h>

#include <locale.h>
#include <stdio.h>
struct TNode
{
	int data; // Інформаційний блок
	struct TNode* next; // Адресний блок
};
typedef struct TNode Node;

void push(Node** head, int data)
{
	Node* NewNode = (Node*)malloc(sizeof(Node));
	NewNode->data = data; // Інформація
	NewNode->next = *head;
	*head = NewNode;
}

void pop(Node** head)
{
	if (*head == NULL)//якщо стек пустий
		return;
	else if ((*head)->next == NULL)// якщо стек містить лише 1 елемент
	{
		free(*head);
		*head = NULL;
	}
	else // якщо стек не пустий і містить більше 1 елементу
	{
		Node* temp = *head;
		*head = (*head)->next;
		free(temp);
	}
}

void print(Node* head)//Виведення стеку на екран
{
	printf("\nStack\n");
	while (head) // Виведення результатів
	{
		printf("%d\n", head->data);
		head = head->next;
	}
}
void main()
{
	Node* head = NULL; // Покажчик, що вказує на голову стеку
	int a,b;
	scanf("%d", &a);
	for (int i = 0; i < a; i++) // Цикл для створення 5 вузлів
	{
		scanf("%d", &b);
		if (b % 2 == 0)
		{
			push(&head, b);
		}
		push(&head, b);
		
		
	}
	// Виведення стеку на екран
	print(head);
	

	return 0;





}
