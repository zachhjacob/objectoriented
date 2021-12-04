package com.byaj;

import java.util.ArrayList; 
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        ArrayList<inventory> stock = new ArrayList<inventory>();
        ArrayList<Purchases> purchase = new ArrayList<Purchases>();


        inventory Inv = new inventory();
        Inv.setItem("Bison Sweater ");
        Inv.setPrice(55.99);
        stock.add(Inv);

        Inv = new inventory();
        Inv.setItem("Bison Tee ");
        Inv.setPrice(14.99);
        stock.add(Inv);

        Inv = new inventory();
        Inv.setItem("Bison Hoodie ");
        Inv.setPrice(23.99);
        stock.add(Inv);

        Inv = new inventory();
        Inv.setItem("Bison Bumpersticker ");
        Inv.setPrice(4.99);
        stock.add(Inv);

        Scanner input = new Scanner(System.in);
        String item;
        double sum = 0.0;
        int index = -1;

        do {
            System.out.println("What item did you buy? if you did not buy anything enter no:  ");
            item = input.nextLine();
            Purchases order = new Purchases();
            for (int i = 0; i < stock.size(); i++) {
                if (stock.get(i).getItem().equals(item)){
                    index = i;
                    String pItem = stock.get(index).getItem();
                    double pPrice = stock.get(index).getPrice();
                    order.setPurchItem(pItem);
                    order.setPurchPrice(pPrice);
                    purchase.add(order);
                }
            }
        } while (!item.equalsIgnoreCase("no"));


        for (int i = 0; i < purchase.size(); i++) {
            System.out.println("Items that I purchased: " + purchase.get(i).getPurchItem());
            double itemPrice=  purchase.get(i).getPurchPrice();
            sum += itemPrice;
        }

        System.out.println("Total Spent: " + sum);

    }
    
