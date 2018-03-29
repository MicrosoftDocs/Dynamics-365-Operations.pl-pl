--- 
title: Tworzenie marszrut (tylko luty 2016)
description: "To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a1da6a38e9e70efdbbd04e85318f208c82ab39ed
ms.contentlocale: pl-pl
ms.lasthandoff: 02/13/2018

---
# <a name="create-routes-february-2016-only"></a>Tworzenie marszrut (tylko luty 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

To zadanie koncentruje się na utworzeniu marszrut produkcji wyrobu gotowego i półproduktu. Jest to piąte zadanie w serii zadań obliczania BOM. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Tworzenie marszruty dla półproduktu
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz towar o numerze BOM_2.  
3. W okienku akcji kliknij pozycję Konstruuj.
4. Kliknij opcję Marszruta.
5. Kliknij przycisk Nowy.
6. Kliknij opcję Marszruta i wersja marszruty.
7. Wypełnij pole Opis.
    * Na przykład wpisz MARSZRUTA_2.  
8. W polu Oddział wprowadź lub wybierz wartość.
    * W tym przykładzie wprowadź lub wybierz oddział 1.  
9. Kliknij przycisk OK.
10. Kliknij przycisk Nowy.
11. W polu Operacja wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Montaż.  
12. W polu Czas procesu wpisz liczbę.
    * Na przykład wpisz 1. Czasy procesów są często uwzględniane w cenach obliczanych dla towarów.  
13. W polu Grupa marszruty wpisz lub wprowadź wartość.
    * W tym przykładzie wybierz opcję Standardowy.  
14. Kliknij kartę Ustawienia.
15. W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Montaż.  
16. Kliknij kartę Czasy.
17. W polu Czas przezbrajania wpisz liczbę.
    * W tym przykładzie wpisz wartość 1. Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.  
18. W okienku akcji kliknij pozycję Wersja marszruty.
19. Kliknij przycisk Zatwierdź.
20. W polu Czy chcesz także zatwierdzić marszrutę? kliknij opcję Tak.
21. Kliknij przycisk OK.
22. W okienku akcji kliknij pozycję Wersja marszruty.
23. Kliknij Aktywacja.
24. Zamknij stronę.
25. Zamknij stronę.

## <a name="create-a-route-for-a-finished-product"></a>Tworzenie marszruty dla wyrobu gotowego
1. Na liście kliknij łącze w wybranym wierszu.
    * Zaznacz towar o numerze BOM_1.  
2. W okienku akcji kliknij pozycję Konstruuj.
3. Kliknij opcję Marszruta.
4. Kliknij przycisk Nowy.
5. Kliknij opcję Marszruta i wersja marszruty.
6. Wypełnij pole Opis.
    * W tym przykładzie wpisz MARSZRUTA_1.  
7. W polu Oddział wprowadź lub wybierz wartość.
    * W tym przykładzie wprowadź lub wybierz oddział 1.  
8. Kliknij przycisk OK.
9. Kliknij przycisk Nowy.
10. W polu Operacja wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Pakowanie.  
11. W polu Czas procesu wpisz liczbę.
    * W tym przykładzie wpisz wartość 1.  
12. W polu Grupa marszruty wpisz lub wprowadź wartość.
    * W tym przykładzie wybierz opcję Standardowy.  
13. Kliknij kartę Ustawienia.
14. W polu Kategoria czasu przezbrajania wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Pakowanie.  
15. Kliknij kartę Czasy.
16. W polu Czas przezbrajania wpisz liczbę.
    * W tym przykładzie wpisz wartość 1.  
17. W okienku akcji kliknij pozycję Wersja marszruty.
18. Kliknij przycisk Zatwierdź.
19. Kliknij przycisk OK.
20. W okienku akcji kliknij pozycję Wersja marszruty.
21. Kliknij Aktywacja.
22. Zamknij stronę.
23. Zamknij stronę.

## <a name="enable-automatic-consumption-of-setup-time"></a>Włączanie automatycznego zużywania czasu przezbrajania
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Marszruty > Grupy marszrut.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Na liście zaznacz pozycję Standardowy.  
3. Kliknij przycisk Edytuj.
4. W polu Czas przezbrajania zaznacz opcję Tak.
    * Czasy przezbrajania są często uwzględniane w cenach obliczanych dla towarów.  
5. Kliknij przycisk Zapisz.
6. Zamknij stronę.


