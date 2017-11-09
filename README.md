# hello-world
DeepDream

import java.util.Random;

public class Main {
    String huase;
    String size;
    static String s[] = {"2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"};

    public Main(String h, String s) {
        huase = h;
        size = s;
    }

    public String toString() {
        return huase + size + "\t";
    }

    public static void xipai1(Main a[]) {
        int b[] = {0, 1, 2, 3};
        Main c[] = new Main[52];
        for (int i = 0; i < a.length; i++) {
            if (a[i].huase.equals("♠")) {
                c[b[0]] = a[i];
                b[0] += 4;
            }
            if (a[i].huase.equals("♣")) {
                c[b[1]] = a[i];
                b[1] += 4;
            }
            if (a[i].huase.equals("♥")) {
                c[b[2]] = a[i];
                b[2] += 4;
            }
            if (a[i].huase.equals("♦")) {
                c[b[3]] = a[i];
                b[3] += 4;
            }
        }
        System.out.println("洗牌1后牌的顺序如下:");
        for (int i = 0; i < 52; i++) {
            System.out.print(c[i]);
            if ((i + 1) % 13 == 0)
                System.out.println();
        }
    }

    public static void xipai2(Main a[]) {
        Main c[] = new Main[52];
        for (int i = 0; i < 52; i++) {
            int t = (int) (Math.random() * (52 - i));
            Main temp = a[t];
            a[t] = a[52 - 1];
            a[52 - 1] = temp;
        }
        System.out.println("洗牌2后牌的顺序如下:");
        for (int i = 0; i < 52; i++) {
            System.out.print(a[i]);
            if ((i + 1) % 13 == 0)
                System.out.println();
        }
    }

    public static void xipai3(Main a[]) {
        Main c[] = new Main[52];
        for (int i = 0; i < 52; i++) {
            int r = (int) (Math.random() * 52);
            if (a[i] != a[r]) {
                Main temp = a[i];
                a[i] = a[r];
                a[r] = temp;
            }

        }
        System.out.println("洗牌3后牌的顺序如下:");
        for (int i = 0; i < 52; i++) {
            System.out.print(a[i]);
            if ((i + 1) % 13 == 0)
                System.out.println();
        }
    }

    public static void main(String[] args) {
        Main a[] = new Main[52];
        for (int i = 0; i < 13; i++) {
            a[i] = new Main("♠", s[i]);
            a[i + 13] = new Main("♣", s[i]);
            a[i + 26] = new Main("♥", s[i]);
            a[i + 39] = new Main("♦", s[i]);
        }
        System.out.println("洗牌前牌的顺序如下:");
        for (int i = 0; i < 52; i++) {
            System.out.print(a[i]);
            if ((i + 1) % 13 == 0)
                System.out.println();
        }
        xipai1(a);
        xipai2(a);
        xipai3(a);


    }
