package com.tamerb.level_1;

import java.util.Arrays;
import java.util.stream.Collectors;

public class QuickSort {

    static final int[] dizi = {10, 5, 3, 4, 1, -2, 278, 0, 2, 6, 7, 8, 9};


    // quick sort algoritması hesaplama fonksiyonu
    public static void hizliSiralama(int[] dizi, int bas, int son) {
        if (dizi.length == 0) {
            System.out.println("Dizi boş");
        }
        if (bas < son) {
            // pivot elemanı seçer büyük, küçük olma durumuna göre  parçalama  işlemi yapar
            int pivot = pivotSecBolumle(dizi, bas, son);
            //  özyinelemeli alt diziyi sırala
            hizliSiralama(dizi, bas, pivot - 1);
            // özyinelemeli üst diziyi sırala
            hizliSiralama(dizi, pivot + 1, son);
        }
    }

    public static int pivotSecBolumle(int[] dizi, int bas, int son) {
        // pivot elemen son öğe olarak seçildi
        int pivot = dizi[son];
        int i = (bas - 1);
        for (int j = bas; j < son; j++) {
            // şimdiki öğe pivot'dan küçükse
            if (dizi[j] <= pivot) {
                i++;
                // mevcut ögeyi daha büyük ile değiştir (sırala)
                int temp = dizi[i];
                dizi[i] = dizi[j];
                dizi[j] = temp;
            }
        }
        // pivotu daha büyük öğe ile değiştirir
        int temp = dizi[i + 1];
        dizi[i + 1] = dizi[son];
        dizi[son] = temp;
        //yolla -->  pivot final index
        return i + 1;
    }

    // diziyi yazdırma için stream api kullandık
    public static void diziYazdir(int[] dizi) {
        System.out.print(Arrays.stream(dizi)
                .mapToObj(String::valueOf)
                .collect(Collectors.joining(" -> ")));
    }

    public static void main(String[] args) {
        System.out.println("Dizi: ");
        diziYazdir(dizi);
        hizliSiralama(dizi, 0, dizi.length - 1);
        System.out.println("\n\nQuick Sort ile sıralanmış hali: ");
        diziYazdir(dizi);
    }

}
