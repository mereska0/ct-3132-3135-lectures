---
sticker: emoji//1f334
---

```
Struct Node 
	int key
	int priority
	Node left // левый сын всегда меньше или равен
	Node right // правый сын всегда больше 
	int sum/size/max/min
	Node(int value)
		key = value
		priority = rand // генерим случайное число
		size = 1
		sum = value
		right = null
		left = null
```


```
<Node, Node> Split(Node root, int value) 
	if (root == null) return <null, null>
	if (root.key >= value) 
	// корень уходит в правое поддерево
		<l_tree, r_tree> = split(root.left,value)
		root.left = r_tree
		update(root)
		return <l_tree,root>

	else
	// корень уходит в левое поддерево
		<l_tree,r_tree> = split(root.right,value)
		root.right = l_tree
		update(root)
		return <root,r_tree>
```


```
// pred: root1 все ключи строго меньше чем все ключи в root2
Node Merge(Node root1, Node root2)
	if (root1 == null) return root2
	if (root2 == null) return root1 
	if (root1.priority > root2.priority) 
		root1.right = merge(root1.right,root2)
		update(root1)
		return root1
	else 
		root2.left = merge(root1, root2.left)
		update(root2)
		return root2
```


```
bool find(Node root, int value)
	if (root == null) return false
	if (root.key == value) return true
	if (root.key < value)
		return find(root.right, value)
	else 
		return find(root.left, value)

```


```
Node insert(Node root, int value)
    if (find(root, value)) return root // если значение уже есть в дереве
    
    Node newNode = new Node(value)  // создать новый узел
    <L, R> = split(root, value)    // L < value, R >= value
    
    return Merge(Merge(L, newNode), R)

```


```
Node erase(Node root, int value)
    if (!find(root, value)) return root
    
    <L, R> = split(root, value)           // L < value, R >= value
    <M, R2> = split(R, value + 1)         // M == value, R2 > value
    
    return Merge(L, R2)
```


```
// такие геттеры будут примнимы ко всем полям Node
int get_size(Node root)
	if(root == null) return 0
	return root.size

```


```
void update(Node root)
	if (root == null) return 
	root.size = get_size(root.left) + get_size(root.right) + 1
```
