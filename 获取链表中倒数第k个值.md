import java.util.Stack;

public class LeetCode05 {

    public static void main(String[] args) {
        LinkNode node = new LinkNode(0);
        node.next = new LinkNode(1);
        node.next.next = new LinkNode(2);
        node.next.next.next = new LinkNode(3);
        printTheNode(node, 1);
    }

    /**
     * 链表中倒数第k个节点
     * （先把链表放到栈里，再取值）
     *
     * @param node
     * @param index
     */
    public static void printTheNode(LinkNode node, int index) {
        Stack<Integer> stack = new Stack<Integer>();
        while (node != null) {
            stack.push(node.val);
            node = node.next;
        }

        if (!stack.isEmpty() && stack.size() >= index) {
            System.out.println(stack.get(stack.size() - index));
        }
    }
}
