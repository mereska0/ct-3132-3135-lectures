---
sticker: emoji//1f332
---
## Задача 
Теперь у нас новая задача мы хотим:
1) делать операцию на полуинтервале 
	*добавить ко всем элементам 2 на полуинтервале* 
2) все также находить какие то значения на полуинтервале 
	*найти минимум на полуинтервале* 
## Структура дерева
дерево теперь хранит ноду из 2 значений:
1) последняя примененная массовая операция 
2) текущее значение дерева 
## Дерево присвоить + сумма 

### Структура ноды 
```
struct Node {
	int modify // тег массовой операции
	int sum // значение на отрезке
}
Node[] tree = new Node()
```

### Modify
присвоим значение value всем элементам отрезка
```
void modify (int value,int l, int r,  int x,  int lx, int rx) {
	if (lx >= r || rx <= l) { // если не в отрезке
		return
	}
	if (lx >= l && rx <= r) { // если узел лежит полностью в отрезке
		tree[x].modify = value
		tree[x].sum =  value*(rx-lx) // все знач изменены на value поэтому sum = val * кол-во элементов
		return
	}
	push(x,lx,rx)
	int mid = (lx + rx)/2
	modify(value,l,r,2x+1, lx,mid)
	modify(value, l,r,2x+2,mid,rx)
	tree[x].sum = tree[2x+1].sum + tree[2x+2].sum
}
```

### Push
информацию что дети поменялись мы даем только родителю и при необходимости уже делаем push к детям

```
// если изменений нет то будет лежать нейтральный элемент - нейтрал(IDT) 
void push(int x, int lx, int rx) {
	/* не пушем когда:
		1. если лист то не пушим 
		2. если не изменений то не пушим
	*/	   
	if (tree[x].modify == IDT) return
	if (rx - lx <= 1){  // лист
        tree[x].modify = IDT
        return
    }    
	int mid = (lx+rx)/2
	tree[2x+1].modify = tree[x].modify
	tree[2x+1].sum = tree[x].modify*(mid - lx) // все знач изменены на value поэтому sum = val * кол-во элементов
	tree[2x+2].modify = tree[x].modify
	tree[2x+2].sum = tree[x].modify * (rx - mid) // все знач изменены на value поэтому sum = val * кол-во элементов

	   
	tree[x].modify = IDT

}

```

## getSum 
получаем сумма на отрезке
```
int getSum(int l, int r, int x, int lx, int rx) {
	if (lx >= r || rx <= l) {
		return 0;
	}
	if (rx <= r && lx >= l) {
		return tree[x].sum
	}
	push(x, lx, rx)
	int mid = (lx + rx)/2
	
	return getSum(l,r,2x+1,lx,mid) + getSum(l,r,2x+2,mid,rx)
	
} 

```
