public class BinarySearchTree {
    static class Node {
        int data;
        Node left;
        Node right;

        Node(int data) {
            this.data = data;
            left = right = null;
        }
    }

    // Insert a node in BST
    public static Node insert(Node root, int val) {
        if (root == null)
            return new Node(val);
        if (val < root.data)
            root.left = insert(root.left, val);
        else if (val > root.data)
            root.right = insert(root.right, val);
        return root;
    }

    // Search a node in BST
    public static boolean search(Node root, int key) {
        if (root == null)
            return false;
        if (root.data == key)
            return true;
        if (key < root.data)
            return search(root.left, key);
        else
            return search(root.right, key);
    }

    // Find the minimum value node
    public static Node findMin(Node root) {
        while (root.left != null) {
            root = root.left;
        }
        return root;
    }

    // Delete a node in BST
    public static Node delete(Node root, int key) {
        if (root == null)
            return root;
        if (key < root.data)
            root.left = delete(root.left, key);
        else if (key > root.data)
            root.right = delete(root.right, key);
        else {
            if (root.left == null)
                return root.right;
            else if (root.right == null)
                return root.left;
            root.data = findMin(root.right).data;
            root.right = delete(root.right, root.data);
        }
        return root;
    }

    // InOrder traversal
    public static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.data + " ");
        inorder(root.right);
    }

    // PreOrder traversal
    public static void preorder(Node root) {
        if (root == null) return;
        System.out.print(root.data + " ");
        preorder(root.left);
        preorder(root.right);
    }

    // PostOrder traversal
    public static void postorder(Node root) {
        if (root == null) return;
        postorder(root.left);
        postorder(root.right);
        System.out.print(root.data + " ");
    }

    public static void main(String[] args) {
        Node root = new Node(10);
        root = insert(root, 5);
        root = insert(root, 15);
        root = insert(root, 7);
        root = insert(root, 19);
        root = insert(root, 20);
        root = insert(root, 3);
        root = insert(root, 4);
        root = insert(root, 1);

        System.out.print("InOrder Traversal: ");
        inorder(root);
        System.out.println();

        System.out.print("PreOrder Traversal: ");
        preorder(root);
        System.out.println();

        System.out.print("PostOrder Traversal: ");
        postorder(root);
        System.out.println();

        System.out.println("Search 7: " + (search(root, 7) ? "Found" : "Not Found"));
        System.out.println("Search 8: " + (search(root, 8) ? "Found" : "Not Found"));

        root = delete(root, 7);
        System.out.print("InOrder Traversal after deletion: ");
        inorder(root);
        System.out.println();
    }
}
