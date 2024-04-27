
#include<iostream>
using namespace std;

struct treenode{
	int data;
	treenode* left, * right;
	treenode(int v):data(v),left(NULL),right(NULL){}
};

void DFS(treenode *root) {
	//递归结束标志
	if (root == NULL)
		return;
	cout << root->data<<" ";
	DFS(root->left);
	DFS(root->right);
}
int main() {
	treenode* root=new treenode(1);
	root->left = new treenode(2);
	root->right = new treenode(3);
	root->left->left = new treenode(4);
	root->left->right = new treenode(5);
	root->right->left = new treenode(6);
	root->right->right = new treenode(7);
	cout << "DFS："<<endl;
	DFS(root);
}
