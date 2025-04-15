# BookMarketJava
import java.util.Scanner;

public class Welcome {

    static final int NUM_BOOK = 3;
    static final int NUM_ITEM = 7;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[][] book = new String[NUM_BOOK][NUM_ITEM];
        BookList(book);

        // Foydalanuvchi ma'lumotlarini olish
        System.out.print("당신의 이름을 입력하세요: ");
        String name = scanner.nextLine();

        System.out.print("전화번호를 입력하세요: ");
        String phone = scanner.nextLine();

        // Xush kelibsiz ekran
        String greeting = "Welcome to Shopping Mall";
        String tagline = "Welcome to Book Market";

        System.out.println("*********");
        System.out.println("\t" + greeting);
        System.out.println("\t" + tagline);
        System.out.println("*********");

        // Menyu
        System.out.println("1. 고객 정보 확인하기 \t4. 장바구니에 항목 추가하기");
        System.out.println("2. 장바구니 상품 목록 보기 \t5. 장바구니의 항목 수량 줄이기");
        System.out.println("3. 장바구니 비우기 \t\t6. 장바구니의 항목 삭제하기");
        System.out.println("7. 영수증 출력 \t\t8. 종료");
        System.out.println("*********");

        // Menyudan tanlov
        System.out.print("원하는 메뉴 번호를 선택하세요: ");
        int choice = scanner.nextInt();
        scanner.nextLine(); // buffer to'ldirish

        if (choice == 4) {
            // Kitoblar ro'yxatini chiqarish
            System.out.println("---------------------------------------------------------");
            for (int i = 0; i < NUM_BOOK; i++) {
                for (int j = 0; j < NUM_ITEM; j++) {
                    System.out.print(book[i][j] + " | ");
                }
                System.out.println();
            }
            System.out.println("---------------------------------------------------------");

            // Kitob tanlash
            System.out.print("추가할 도서의 ISBN을 입력하세요: ");
            String isbn = scanner.nextLine();

            // ISBN asosida kitobni qidirish va savatchaga qo‘shish
            boolean found = false;
            for (int i = 0; i < NUM_BOOK; i++) {
                if (book[i][0].equals(isbn)) {
                    System.out.println(book[i][0] + " 도서가 장바구니에 추가되었습니다.");
                    found = true;
                    break;
                }
            }

            if (!found) {
                System.out.println("해당 ISBN의 도서를 찾을 수 없습니다.");
            }
        }

        scanner.close();
    }

    // Kitoblar ro'yxatini to'ldirish
    public static void BookList(String[][] book) {
        // 1-kitob
        book[0][0] = "ISBN1234";
        book[0][1] = "쉽게 배우는 JSP 웹 프로그래밍";
        book[0][2] = "27000";
        book[0][3] = "홍길동";
        book[0][4] = "단계별 쇼핑몰을 구현하며 배우는 JSP 웹 프로그래밍";
        book[0][5] = "IT전문서";
        book[0][6] = "2018/10/08";

        // 2-kitob
        book[1][0] = "ISBN1235";
        book[1][1] = "안드로이드 프로그래밍";
        book[1][2] = "33000";
        book[1][3] = "우재남";
        book[1][4] = "실습 단계별 명쾌한 멘토링";
        book[1][5] = "IT전문서";
        book[1][6] = "2022/01/22";

        // 3-kitob
        book[2][0] = "ISBN1236";
        book[2][1] = "스크래치";
        book[2][2] = "22000";
        book[2][3] = "고광일";
        book[2][4] = "컴퓨팅 사고력을 키우는 블록 코딩";
        book[2][5] = "컴퓨터입문";
        book[2][6] = "2019/06/10";
    }
}