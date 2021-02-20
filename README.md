#include<iostream>
#include<map>
#include<queue>
using namespace std;
class tree{
    private:
        int data;
        tree *left,*right;
        
    public:
        tree(int val){ //constructor
            this->data = val;
            this->left = this->right = NULL;
        }
        tree *insert(tree *root,int val){
            if(root==NULL)
            {
                return new tree(val);
            }
            if(val<root->data){
                root->left = insert(root->left,val);
            }
            if(val>root->data){
                root->right = insert(root->right,val);
            }
            return root;
        }
        void inorder(tree *root){
         //   cout<<"Inorder Traversal"<<endl;
            if(root==NULL){
                return;
            }
            inorder(root->left);
            cout<<root->data<<" ";
            inorder(root->right);
        }
        void preorder(tree *root){
            
              if(root==NULL){
                return;
            }
            cout<<root->data<<" ";
            preorder(root->left);
            preorder(root->right);
        
        }
};
int main(){
    tree *root = NULL;
    root = root->insert(root,5);
    root = root->insert(root,8);
    root = root->insert(root,4);
    root = root->insert(root,6);
    root = root->insert(root,10);
    cout<<"Inorder Traversal"<<endl;
    root->inorder(root);
    cout<<"\n"<<"Preorder Traversal"<<endl;
    root->preorder(root);
    return 0;
}
