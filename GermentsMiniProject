package com.mycompany.main;

import java.util.ArrayList;
import java.util.Scanner;

// Garment class to represent each garment item
class Garment {
    private final String name;
    private final String type;
    private final double price;
    private int stock;

    public Garment(String name, String type, double price, int stock) {
        this.name = name;
        this.type = type;
        this.price = price;
        this.stock = stock;
    }

    public String getName() {
        return name;
    }

    public String getType() {
        return type;
    }

    public double getPrice() {
        return price;
    }

    public int getStock() {
        return stock;
    }

    public void setStock(int stock) {
        this.stock = stock;
    }

    public void displayInfo() {
        System.out.println("Garment Name: " + name);
        System.out.println("Type: " + type);
        System.out.println("Price: $" + price);
        System.out.println("Stock: " + stock);
    }
}

// GarmentManagementSystem class to handle all operations
class GarmentManagementSystem {
    private final ArrayList<Garment> garments;
    private final Scanner scanner;

    public GarmentManagementSystem() {
        garments = new ArrayList<>();
        scanner = new Scanner(System.in);
    }

    public void addGarment() {
        System.out.print("Enter garment name: ");
        String name = scanner.nextLine();
        System.out.print("Enter garment type: ");
        String type = scanner.nextLine();
        System.out.print("Enter garment price: ");
        double price = scanner.nextDouble();
        System.out.print("Enter stock quantity: ");
        int stock = scanner.nextInt();
        scanner.nextLine(); // consume newline

        Garment garment = new Garment(name, type, price, stock);
        garments.add(garment);
        System.out.println("Garment added successfully!");
    }

    public void viewAllGarments() {
        if (garments.isEmpty()) {
            System.out.println("No garments available.");
        } else {
            for (Garment garment : garments) {
                garment.displayInfo();
                System.out.println("----------------------");
            }
        }
    }

    public void updateStock() {
        System.out.print("Enter the name of the garment to update stock: ");
        String name = scanner.nextLine();
        for (Garment garment : garments) {
            if (garment.getName().equalsIgnoreCase(name)) {
                System.out.print("Enter new stock quantity: ");
                int stock = scanner.nextInt();
                scanner.nextLine(); // consume newline
                garment.setStock(stock);
                System.out.println("Stock updated successfully!");
                return;
            }
        }
        System.out.println("Garment not found.");
    }

    public void run() {
        while (true) {
            System.out.println("=== Garment Management System ===");
            System.out.println("1. Add Garment");
            System.out.println("2. View All Garments");
            System.out.println("3. Update Stock");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // consume newline

            switch (choice) {
                case 1 -> addGarment();
                case 2 -> viewAllGarments();
                case 3 -> updateStock();
                case 4 -> {
                    System.out.println("Exiting system.");
                    return;
                }
                default -> System.out.println("Invalid option. Try again.");
            }
        }
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        GarmentManagementSystem gms = new GarmentManagementSystem();
        gms.run();
    }
}
