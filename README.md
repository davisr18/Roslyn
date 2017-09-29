# Roslyn
#pragma once

class RegisterQueue{//where the linked list happens
private:
  struct
};
struct Node {
    Node * next;
    T value;
    //  next = NULL(empty), "this" is a constructor that makes the empty node the default
    Node(T value, Node * next = NULL) {
      this -> next = next;
      this -> value = value;
    }
  };
  Node * head;
  Node * rear;

public:

  int numberOfCustomers=0;
  int maxLineLength=0;

  RegisterQueue() {
   head = NULL;
   rear=NULL;

  }
  ~RegisterQueue() {//deconstructor so we can avoid a memory leak
    if (front) {
      Node * front = head -> next;
      Node * follow = head;
      while(head) {
        delete(follow);
        follow = front;
        front = front -> next;
      }
      delete(follow);
    }

    }
  }
  void enqueue(T value) {
    head = new Node(value, head);
    rear=head;
  }

  void dequeue{
    T pop() {
      T item = head -> value;
      Node * temp = head;
      head = head -> next;
      delete(temp);
      return item;
    }
    void pop(T item) { // Remove this value from list
      if (!head) return;
      if (head->value == item) {
        T item = pop();
        return;
      }
      Node *lead = head->next;
      Node *follow = head;
      while (lead) {
        if (lead->value == item){
          follow->next = lead->next;
          delete lead; // Prevent mem leak
          return;
        }
        lead = lead->next;
        follow = follow->next;
      }
    }

    T get(int index) {
    }
  }
