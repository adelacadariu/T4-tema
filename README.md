#include <stdio.h>
#include <stdlib.h>

typedef struct transf
{
	int bit;
	struct transf *urm;
}nod;
nod *adaugare(nod *prim, int bit)
{
	nod *p;
	p = (nod*)malloc(sizeof(nod));
	p->bit = bit;
	p->urm = prim;
	prim = p;
	return prim;
	
}
void afisare(nod *prim)
{
	nod *q;
	int contor = 0;
	for (q = prim; q != NULL; q = q->urm)
		printf("%d", q->bit);
	printf("\n");

}
int main()
{
	nod *prim;
	int n, r;
	prim = NULL;
	scanf("%d", &n);
	while (n != 0)
	{
		r = n % 2;
		prim = adaugare(prim, r);
		n= n/ 2;
	}
	afisare(prim);
	system("pause");
	return 0;
}
