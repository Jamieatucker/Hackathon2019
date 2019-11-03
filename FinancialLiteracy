import java.util.Random;
import java.util.Scanner;

/**
 * Hack OHI/O 2019: Financial Literacy Project for JPMorgan & Chase Co.
 *
 * @author Jamie Tucker, Oskar Klear, William Delo
 *
 */
public final class FinancialLiteracy {

    // Fields so all the methods can access the variables throughout the levels
    public static int money;
    public static int finalMoney;
    public static int housePayment;
    public static int carPayment;
    public static int fuelPayment;
    public static int children;
    public static int clothingValue;
    public static int healthInsuranceValue;
    public static int childHealthInsuranceValue;
    public static int carInsuranceValue;
    public static int houseInsuranceValue;
    public static int foodValue;
    public static boolean hasHealthInsurance;
    public static boolean hasChildHealthInsurance;
    public static boolean hasCarInsurance;
    public static boolean hasHouseInsurance;
    public static boolean hasBirthday;

    private FinancialLiteracy() {

    }

    /**
     * Main method.
     *
     * @param args
     *            the command line arguments
     */
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        // Money Options (0-5)
        int[] moneyOptions = { 30000, 45000, 55000, 70000, 84000, 95000, 120000,
                170000, 200000 };
        int[] childrenOptions = { 0, 1, 2, 3 };
        money = moneyOptions[(int) (Math.random() * moneyOptions.length)];
        finalMoney = money;
        children = childrenOptions[(int) (Math.random()
                * childrenOptions.length)];
        // We need food, clothes, house, car, insurance, kids
        // Account for debt, random events, etc.
        System.out.println(
                "Welcome to the Financial Literacy Game! You will be given a set amount of money and children and will budget your money depending on the situations ahead.");
        System.out.println(
                "The prices that you see for certain items are averages and may be subject to change as time passes.");
        System.out.println("\nHere is your life to plan for the future.");
        System.out.println("You have $" + money + " for the year.");
        System.out
                .println("You have " + children + " children to account for.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        firstLevel();
        secondLevel();
        thirdLevel();
        fourthLevel();
        fifthLevel();
        runSimulation();
        /*
         * Close input stream
         */
        in.close();
    }

    /**
     * Level one: Select house
     *
     */
    private static void firstLevel() {
        Scanner in = new Scanner(System.in);
        System.out.println(
                "\n/////////////////////////" + "\n/// Select your House ///\n"
                        + "/////////////////////////\n");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("You have $" + money + " left for the year.");
        int[] costs = { 450, 800, 1050, 1650 };
        System.out.println("You must select a home.");
        // Trailer, one-bed apartment, two-bed apartment, four-bed house
        int choice = 0;
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println(
                "Your options include a trailer, a one bedroom apartment, a two bedroom apartment, and a four bedroom house.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("Which option would you prefer?");
        System.out.println(
                "1: Trailer - $450 a month, small, dirty, but affordable.");
        System.out.println(
                "2: One bedroom apartment - $800 a month, small, but livable. Room for 3 people total if you squeeze");
        System.out.println(
                "3: Two bedroom apartment - $1050 a month, more space than a one bedroom apartment, nice quality, room enough for 3-4 people.");
        System.out.println(
                "4: A house - $1650 a month, very spacious, in a nice neighborhood, can fit several people comfortably.");
        System.out.println(
                "Please enter the number of which living space you would like: ");
        choice = in.nextInt();
        if (children > 2 && choice <= 2) {
            while (choice <= 2) {
                System.out.println(
                        "You cannot fit three children into that small place. You must choose a larger home.");
                choice = in.nextInt();
            }

        }
        while (!(1 <= choice && choice <= 4)) {
            System.out.println("Please enter a number between 1-4.");
            choice = in.nextInt();
            if (children > 2 && choice <= 2) {
                while (choice < 2) {
                    System.out.println(
                            "You cannot fit three children into that small place. You must choose a larger home.");
                    choice = in.nextInt();
                }

            }
        }
        housePayment = (costs[choice - 1]);
        money -= (costs[choice - 1]) * 12;
    }

    /**
     * Level two: Choose a car
     */
    private static void secondLevel() {
        Scanner in = new Scanner(System.in);
        int choice = 0;
        String car = "";
        String condition = "";
        // number of choices to make for the cars
        int[] cars = { 1, 2, 3, 4, 5 };
        System.out.println(
                "\n/////////////////////////" + "\n/// Select your Car /////\n"
                        + "/////////////////////////\n");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("You have $" + money + " remaining.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println(
                "You must select a car to drive around. This is for a 5 year lease.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println(
                "Here are your options: compact, SUV, Sudan, mini-van, exotic");
        System.out.println("Each car can be bought as used or new.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        // NEW: compact = 250, sedan = 300, SUV = 450, mini-van = 750
        while (choice <= 0 || choice > cars.length + 1) {
            System.out.println(
                    "Which car would you like to buy? \n1. Compact 2. SUV 3. Sedan 4. Mini-van 5. Exotic");
            choice = in.nextInt();
            int decision = 0;
            switch (choice) {
                case 1:
                    car = "compact";
                    fuelPayment = 117;
                    System.out.println(
                            "Which condition of the compact car are you buying? \n1. Used 2. New");
                    decision = in.nextInt();
                    if (decision == 1) {
                        condition = "used";
                        carPayment = 140;
                        money -= 2000;
                        System.out
                                .println("Your down payment is $" + 2000 + ".");
                        money -= (carPayment * 12);
                    } else if (decision == 2) {
                        condition = "new";
                        carPayment = 250;
                        money -= 4000;
                        System.out
                                .println("Your down payment is $" + 4000 + ".");
                        money -= (carPayment * 12);
                    } else {
                        System.out.println(
                                "Since you decided to not follow the directions, you lose $1000 and your condition is defaulted as used!");
                        // Delay the text
                        try {
                            Thread.sleep(2000);
                        } catch (InterruptedException ex) {
                        }
                        money -= 1000;
                        money -= 2000;
                        System.out
                                .println("Your down payment is $" + 2000 + ".");
                        condition = "used";
                        carPayment = 125;
                        money -= (carPayment * 12);
                    }
                    break;
                case 2:
                    car = "sedan";
                    fuelPayment = 170;
                    System.out.println(
                            "Which condition of the sedan are you buying? \n1. Used 2. New");
                    decision = in.nextInt();
                    if (decision == 1) {
                        condition = "used";
                        carPayment = 295;
                        money -= 2500;
                        System.out
                                .println("Your down payment is $" + 2500 + ".");
                        money -= (carPayment * 12);
                    } else if (decision == 2) {
                        condition = "new";
                        carPayment = 550;
                        money -= 5000;
                        System.out
                                .println("Your down payment is $" + 5000 + ".");
                        money -= (carPayment * 12);
                    } else {
                        System.out.println(
                                "Since you decided to not follow the directions, you lose $1000 and your condition is defaulted as used!");
                        // Delay the text
                        try {
                            Thread.sleep(2000);
                        } catch (InterruptedException ex) {
                        }
                        money -= 1000;
                        money -= 2500;
                        System.out
                                .println("Your down payment is $" + 2500 + ".");
                        condition = "used";
                        carPayment = 175;
                    }
                    break;
                case 3:
                    car = "SUV";
                    fuelPayment = 200;
                    System.out.println(
                            "Which condition of the SUV are you buying? \n1. Used 2. New");
                    decision = in.nextInt();
                    if (decision == 1) {
                        condition = "used";
                        carPayment = 475;
                        money -= 2500;
                        System.out
                                .println("Your down payment is $" + 2500 + ".");
                        money -= (carPayment * 12);
                    } else if (decision == 2) {
                        condition = "new";
                        carPayment = 700;
                        money -= 5000;
                        System.out
                                .println("Your down payment is $" + 5000 + ".");
                        money -= (carPayment * 12);
                    } else {
                        System.out.println(
                                "Since you decided to not follow the directions, you lose $1000 and your condition is defaulted as used!");
                        // Delay the text
                        try {
                            Thread.sleep(2000);
                        } catch (InterruptedException ex) {
                        }
                        money -= 1000;
                        money -= 2500;
                        System.out
                                .println("Your down payment is $" + 2500 + ".");
                        condition = "used";
                        carPayment = 135;
                    }
                    break;
                case 4:
                    car = "mini-van";
                    fuelPayment = 225;
                    System.out.println(
                            "Which condition of the mini-van are you buying? \n1. Used 2. New");
                    decision = in.nextInt();
                    if (decision == 1) {
                        condition = "used";
                        carPayment = 450;
                        money -= 3200;
                        System.out
                                .println("Your down payment is $" + 3200 + ".");
                        money -= (carPayment * 12);
                    } else if (decision == 2) {
                        condition = "new";
                        carPayment = 900;
                        money -= 6400;
                        System.out
                                .println("Your down payment is $" + 6400 + ".");
                        money -= (carPayment * 12);
                    } else {
                        System.out.println(
                                "Since you decided to not follow the directions, you lose $1000 and your condition is defaulted as used!");
                        // Delay the text
                        try {
                            Thread.sleep(2000);
                        } catch (InterruptedException ex) {
                        }
                        money -= 1000;
                        money -= 3200;
                        System.out
                                .println("Your down payment is $" + 3200 + ".");
                        condition = "used";
                        carPayment = 700;
                    }
                    break;
                case 5:
                    car = "lamborghini";
                    fuelPayment = 400;
                    System.out.println(
                            "Which condition of the mini-van are you buying? \n1. Used 2. New");
                    decision = in.nextInt();
                    if (decision == 1) {
                        condition = "used";
                        carPayment = 1416;
                        money -= 9400;
                        System.out
                                .println("Your down payment is $" + 3200 + ".");
                        money -= (carPayment * 12);
                    } else if (decision == 2) {
                        condition = "new";
                        carPayment = 5310;
                        money -= 35400;
                        System.out.println(
                                "Your down payment is $" + 35400 + ".");
                        money -= (carPayment * 12);
                    } else {
                        System.out.println(
                                "Since you decided to not follow the directions, you lose $1000 and your condition is defaulted as used!");
                        // Delay the text
                        try {
                            Thread.sleep(2000);
                        } catch (InterruptedException ex) {
                        }
                        money -= 1000;
                        money -= 3200;
                        System.out
                                .println("Your down payment is $" + 3200 + ".");
                        condition = "used";
                        carPayment = 700;
                    }
                    break;
            }
            System.out.println(
                    "You have selected the " + condition + " " + car + ".");
        }
    }

    /**
     * Level three: Clothes
     */
    private static void thirdLevel() {
        System.out.println(
                "\n/////////////////////////" + "\n/// Select your Clothes /\n"
                        + "/////////////////////////\n");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("You have $" + money + " left for the year.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        int[] costs = { 50, 200, 450, 1600 };
        Scanner in = new Scanner(System.in);
        int choice = 0;

        System.out.println(
                "You can choose to buy clothes from a thrift store, discount stores, casual stores, and designer stores.");
        System.out.println("Which option would you prefer?");
        System.out.println(
                "1: Thrifted - $" + costs[0] + ": cheap, worn clothes.");
        System.out.println("2: Discount - $" + costs[1]
                + ": cheap, not great clothes, but at least they look presentable.");
        System.out.println("3: Casual - $" + costs[2]
                + ": affordable, nice, and new clothing.");
        System.out.println("4: Designer - $" + costs[3]
                + ": expensive, luxury materials, and stylish.");
        System.out.println(
                "Please enter the number of which clothing you would like for you and any children: ");
        choice = in.nextInt();
        while (!(1 <= choice && choice <= 4)) {
            System.out.println("You must enter a number between 1-4.");
            choice = in.nextInt();
        }
        if (children == 0) {
            money = money - (costs[choice - 1]) * 12;
            clothingValue = (costs[choice - 1]);
        } else {
            money = money - (costs[choice - 1] * children) * 12;
            clothingValue = (costs[choice - 1] * children);
        }
        System.out.println(
                "Based on your choice and number of children, your clothing payment for the year is $"
                        + ((costs[choice - 1] * (children + 1)) * 12));
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
    }

    /**
     * Level four: Food
     */
    private static void fourthLevel() {
        System.out.println(
                "\n/////////////////////////" + "\n/// Select your Food ////\n"
                        + "/////////////////////////\n");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("You have $" + money + " left for the year.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println(
                "Select a monthly grocery plan for you and any children you may have.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        int[] costs = { 150, 215, 300 };
        Scanner in = new Scanner(System.in);
        int choice = 0;

        System.out.println(
                "You can choose to buy junk food, normal food, or healthy organic food.");
        System.out.println("Which option would you prefer?");
        System.out.println(
                "1: Junk Food - $" + costs[0] + ": cheap, unhealthy food.");
        System.out.println("2: Regular - $" + costs[1]
                + ": food that is nothing special.");
        System.out.println(
                "3: Organic - $" + costs[2] + ": expensive, healthy food. ");
        System.out.println(
                "Please enter the number of which grocery plan you would like for you and any children you may have: ");
        choice = in.nextInt();
        while (!(1 <= choice && choice <= 3)) {
            System.out.println("You must enter a number between 1-3.");
            choice = in.nextInt();
        }
        if (children == 0) {
            money -= (costs[choice - 1]) * 12;
            foodValue = (costs[choice - 1]);
        } else {
            money -= (costs[choice - 1] * (children + 1)) * 12;
            foodValue = (costs[choice - 1] * (children + 1));
        }
        System.out.println(
                "Based on your choice and number of children, your grocery payment for the year is $"
                        + ((costs[choice - 1] * (children + 1)) * 12));
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
    }

    /**
     * Level five: Insurance
     */
    private static void fifthLevel() {
        System.out.println("\n/////////////////////////////"
                + "\n/// Select your Insurance ///\n"
                + "/////////////////////////////\n");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        System.out.println("You have $" + money + " remaining.");
        // Delay the text
        try {
            Thread.sleep(2000);
        } catch (InterruptedException ex) {
        }
        Scanner in = new Scanner(System.in);
        // 1 = Your health insurance, 2 = children health insurance, 3 = car insurance, 4 = House insurance
        int choice = 0;
        while (choice != 5) {
            if (children > 0) {
                System.out.println(
                        "Pick one insurance you would like: \n 1. Your health insurance 2. Child health insurance 3. Car insurance 4. House insurance 5. Exit");
                choice = in.nextInt();
                if (choice == 1 && hasHealthInsurance == false) {
                    healthInsuranceValue = 320;
                    money -= healthInsuranceValue * 12;
                    System.out.println("You have acquired health insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {

                    }
                    hasHealthInsurance = true;
                }
                if (choice == 2 && hasChildHealthInsurance == false) {
                    childHealthInsuranceValue = 250;
                    money -= (childHealthInsuranceValue * children) * 12;
                    System.out.println(
                            "You have acquired child health insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasChildHealthInsurance = true;
                }
                if (choice == 3 && hasCarInsurance == false) {
                    carInsuranceValue = 1000;
                    money -= 1000 * 12;
                    System.out.println("You have acquired car insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasCarInsurance = true;
                }
                if (choice == 4 && hasHouseInsurance == false) {
                    houseInsuranceValue = 1200;
                    money -= 1200 * 12;
                    System.out.println("You have acquired house insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasHouseInsurance = true;
                }
            } else {
                System.out.println(
                        "Which insurance would you like? \n 1. Your health insurance 2. N/A 3. Car insurance 4. House insurance 5. Exit");
                choice = in.nextInt();
                if (choice == 1 && hasHealthInsurance == false) {
                    money -= 320 * 12;
                    healthInsuranceValue = 320;
                    System.out.println("You have acquired health insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasHealthInsurance = true;
                }
                if (choice == 2) {
                    System.out.println(
                            "You have no children, so you cannot receive child health insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                }
                if (choice == 3 && hasCarInsurance == false) {
                    money -= 1000 * 12;
                    carInsuranceValue = 1000;
                    System.out.println("You have acquired car insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasCarInsurance = true;
                }
                if (choice == 4 && hasHouseInsurance == false) {
                    money -= 1200 * 12;
                    houseInsuranceValue = 1200;
                    System.out.println("You have acquired house insurance.\n");
                    // Delay the text
                    try {
                        Thread.sleep(1000);
                    } catch (InterruptedException ex) {
                    }
                    hasHouseInsurance = true;
                }
            }
        }
    }

    private static int randomEvents(int salary) {
        Random rand = new Random();
        int num = 0;
        if (salary <= 30000) {
            num = 1 + rand.nextInt(23);
        } else if (salary <= 45000) {
            num = 1 + rand.nextInt(24);
        } else if (salary <= 56000) {
            num = 1 + rand.nextInt(26);
        } else if (salary <= 70000) {
            num = 1 + rand.nextInt(29);
        } else if (salary <= 84000) {
            num = 1 + rand.nextInt(32);
        } else if (salary <= 120000) {
            num = 1 + rand.nextInt(35);
        } else if (salary <= 200000) {
            num = 1 + rand.nextInt(38);
        }
        switch (num) {
            case 1:
                System.out.println(
                        "Your boss has noticed you staying late and working harder, leading to a promotion!");
                finalMoney += 500;
                break;
            case 2:
                System.out.println(
                        "Congratulations! You just won $500 from your local lottery event!");
                finalMoney += 500;
                break;
            case 4:
                if (hasBirthday == false) {
                    System.out.println(
                            "It's your birthday today! Your family and friends have given you presents resulting in a total of $1500!");
                    finalMoney += 1500;
                    hasBirthday = true;
                }
                break;
            case 5:
                System.out.println(
                        "Oh no! Your car's engine gave out on your way to work!");
                if (hasCarInsurance == true) {
                    System.out.println(
                            "But since you have car insurance, it will pay to cover the damages! Your car insurance is going to increase however.");
                    carInsuranceValue += 500;
                } else {
                    System.out
                            .println("It's going to cost $7500 to repair it!");
                    finalMoney -= 7500;
                }
                break;
            case 8:
                System.out.println(
                        "Oh this is bad! Your house began flooding after a harsh hurricane!");
                if (hasHouseInsurance == true) {
                    System.out.println(
                            "But since you have house insurance, it's only going to cost $2500 to fix the damages!");
                    finalMoney -= 2500;
                } else {
                    System.out.println("It's going to cost $7500!");
                    finalMoney -= 7500;
                }
                break;
            case 9:
                if (children > 0) {
                    System.out
                            .println("Your child has come down with the flu.");
                    if (hasChildHealthInsurance == true) {
                        System.out.println(
                                "But since you bought health insurance for your children, It's only going to cost $200!");
                        finalMoney -= 200;
                    } else {
                        System.out.println("It's going to cost you $600!");
                        finalMoney -= 600;
                    }
                } else {
                    System.out.println("You have come down with the flu.");
                    if (hasHealthInsurance == true) {
                        System.out.println(
                                "But since you have health insurance, its only going to cost $200!");
                        finalMoney -= 200;
                    } else {
                        System.out.println(
                                "Medical treatment is going to cost $600!");
                        finalMoney -= 600;
                    }
                }
                break;
            case 12:
                System.out.println(
                        "Your great grandma has recently passed away. It's going to cost $365 to fly down and mourn the loss.");
                finalMoney -= 365;
                break;
            case 16:
                System.out.println(
                        "You go on vacation and gambled away $10,000! Learn some self-control!");
                finalMoney -= 10000;
                break;
            case 19:
                System.out.println(
                        "You break your arm while falling down the stairs at home!");
                if (hasHealthInsurance == true) {
                    System.out.println(
                            "But since you have health insurance, it will only cost $250!");
                    finalMoney -= 250;
                } else {
                    System.out.println(
                            "It'll cost $2,500 without health insurance!");
                    finalMoney -= 2500;
                }
                break;
            case 22:
                System.out.println(
                        "You find out that you contracted HIV. You need to buy medication!");
                if (hasHealthInsurance == true) {
                    System.out.println(
                            "But since you have health insurance, the additonal monthly medical bill will only be $1000 more!");
                    finalMoney -= 1000;
                    healthInsuranceValue += 1000;
                } else {
                    System.out.println(
                            "It'll add $1,666 to your health insurance!");
                    finalMoney -= 1666;
                    healthInsuranceValue -= 1666;
                }
                break;
            case 23:
                if (children <= 0) {
                    System.out.println(
                            "You take out a nice beautiful/handsome person to a five-star restaurant. You split the bill with them.");
                    finalMoney -= 50;
                } else {
                    System.out.println(
                            "You take the kids out to Luck Y. Bee's. It costs you $10 per child.");
                    finalMoney -= (children * 10);
                }
                break;
        }
        return num;
    }

    private static void runSimulation() {
        boolean passed = true;
        System.out.println(
                "You have made all of your choices. Let's see how this year goes.");
        System.out.println("You have $" + finalMoney + " for this year.");
        for (int i = 1; i <= 12; i++) {
            System.out.println("");
            System.out.println("Month " + i);
            System.out.println("");
            // A random event may occur that can screw up the decisions made!
            randomEvents(finalMoney);
            System.out.println("You have $" + finalMoney + " left this year.");
            System.out.println("You pay your house payment for the month of $"
                    + housePayment);
            System.out.println(
                    "You pay your car payment for the month of $" + carPayment);
            System.out
                    .println("You pay your gas fuel payment for the month of $"
                            + fuelPayment);
            System.out
                    .println("You pay your clothing payment for the month of $"
                            + clothingValue);
            System.out.println(
                    "You pay your health insurance payment for the month of $"
                            + healthInsuranceValue);
            System.out.println(
                    "You pay your child health insurance payment for the month of $"
                            + (childHealthInsuranceValue * children));
            System.out.println(
                    "You pay your car insurance payment for the month of $"
                            + carInsuranceValue);
            System.out.println(
                    "You pay your house insurance payment for the month of $"
                            + houseInsuranceValue);
            System.out.println("You pay your grocery payment for the month of $"
                    + foodValue);
            finalMoney = finalMoney - (housePayment + carPayment + clothingValue
                    + healthInsuranceValue + childHealthInsuranceValue
                    + carInsuranceValue + houseInsuranceValue + foodValue);
            System.out
                    .println("Your money after the payments is $" + finalMoney);
            if (finalMoney <= 0) {
                System.out
                        .println("\nOh no! You ran out of money for the year!");
                System.out.println("You went $" + Math.abs(finalMoney)
                        + " over the budget!");
                System.out.println("You only made it " + i
                        + " months on your yearly salary because of your choices.");
                passed = false;
                break;
            }
            // Delay the text
            try {
                Thread.sleep(3000);
            } catch (InterruptedException ex) {
            }
        }
        if (passed) {
            System.out.println("\nYou made it through the year with $"
                    + finalMoney + " remaining! Congratulations!");
        }
    }

}
