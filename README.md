# Partially Persistent Binary Search Tree

## Overview

This project implements a **Partially Persistent Binary Search Tree** (BST) for efficiently storing data with accessible previous tree versions using Asteroid programming language. The algorithm supports operations to insert, delete, and search for nodes, while maintaining previous tree states. It also includes a terminal-based user interface to demonstrate its functionality, specifically for managing gym member data.

## Key Features

- **Insert**: Add a new node to the most recent version of the tree.
- **Contains**: Search for a node in a specific version of the tree.
- **Delete**: Remove a node from the most recent version of the tree.
- **Versioning**: Access previous versions of the tree after each modification (insert/delete).
- **Terminal Interface**: A simple user interface that allows users to input, delete, and search for gym members over time.

## Project Structure

The project consists of four main files:

- **main.ast**: Contains the user interface logic, allowing for interaction with the data structure.
- **partially_persistent_bst.ast**: Implements the core functionality of the Partially Persistent Binary Search Tree, using the `PartiallyPersistentSet` structure.
- **unit_tests.ast**: Contains smoke tests to verify the correct behavior of the `insert` and `delete` operations across various tree scenarios.
- **PartiallyPersistentSet**: The core data structure that holds the tree’s roots, manages updates, and supports recursive operations.

## Algorithm Details

### Insert(x)
- Inserts `x` into the most recent tree version.
- Recursively places `x` in the correct position, creating a new node with updated left or right children.
- Adds the new root node to the maintained list of tree roots.

### Contains(x, t)
- Checks if `x` exists in the tree at version `t`.
- Recursively searches through the tree, comparing `x` with the current root and traversing left or right based on comparisons.

### Delete(x)
- Removes `x` from the most recent tree version.
- If `x` is a leaf node, it is simply removed.
- If `x` has one child, the child is connected to the parent node.
- If `x` has two children, it is replaced with its inorder successor, creating new nodes where needed.

## Example Use Cases

1. **Deleting a Leaf Node**: After inserting three members and deleting one (a leaf), you can observe the changes in tree versions, confirming that the deleted node is no longer in the latest version but exists in the second-to-last version.
   
2. **Deleting a Node with One Child**: Inserting and deleting a node with one child, ensuring the structure is updated correctly in the previous and current tree versions.
   
3. **Deleting a Node with Two Children**: Deleting a node with two children and ensuring the tree is properly updated, while verifying the integrity of other tree nodes.
   
4. **Deleting a List of Names**: The system can handle batch deletion, and the changes across multiple tree versions can be observed.

## How to Run

1. Clone this repository:
    ```
    git clone <[repository-url](https://github.com/jessicatingley/partially-persistent-bst.git)>
    ```
2. Run the `main.ast` file using your preferred functional programming environment.
3. Interact with the terminal interface to:
   - Insert gym members.
   - Delete individual or batches of members.
   - Search for members in different tree versions.

## Unit Tests

Unit tests are provided to verify the correctness of the tree’s insert and delete operations across various scenarios. To run the tests:
1. Open `unit_tests.ast`.
2. Execute the tests to check the functionality of tree operations.

## Conclusion

This project demonstrates the use of **functional programming** principles and **immutable data structures** to create a **partially persistent binary search tree**. By avoiding mutations and creating new tree versions for each operation, the solution aligns with functional programming paradigms. The implementation highlights the importance of recursive design and multi-paradigm programming.

## Author

Jessica Tingley
