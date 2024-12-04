# DoublyLinked
import java.util.*;
public class DLL{
    class Node{
        int data;
        Node prev;
        Node next;
        Node(int data){
            this.data=data;
            prev=null;
            next=null;
        }
    }
    Node head=null,tail=null;
    public void addatBegin(int data){
        Node newnode=new Node(data);
        if(head==null){
            head=tail=newnode;
        }
        else{
            tail.next=newnode;
            newnode.prev=tail;
            tail=newnode;
        }
    }
    public void insert(int data){
        Node newnode=new Node(data);
        newnode.next=head;
        head.prev=newnode;
        head=newnode;
    }
    public void insertatEnd(int data){
        Node newnode=new Node(data);
        Node temp=head;
        while(temp!=null){
            temp=temp.next;
        }
        tail.next=newnode;
        newnode.prev=tail;
        tail=newnode;
    }
    public void insertatposition(int data){
        Node newnode=new Node(data);
        Node temp1=head,temp2=head;
        Scanner s=new Scanner(System.in);
        System.out.println("Enter position: ");
        int pos=s.nextInt();
        int i=0;
        while(i<pos){
            temp1=temp2;
            temp2=temp2.next;
            i++;
        }
        newnode.prev=temp1;
        temp1.next=newnode;
        newnode.next=temp2;
        temp2.prev=newnode;
    }
    public void display(){
        Node temp=head;
        if(head==null)
        System.out.println("List is Empty");
        while(temp!=null){
            System.out.print(temp.data+" ");
            temp=temp.next;
        }
    }
    public static void main(String args[]){
        DLL dList = new DLL();  
        dList.addatBegin(1);  
        dList.addatBegin(2);  
        dList.addatBegin(3);  
        dList.addatBegin(4);  
        dList.addatBegin(5);
        dList.insert(13);
        dList.insertatEnd(25);
        dList.insertatposition(50);
        dList.display();  
    }
}
