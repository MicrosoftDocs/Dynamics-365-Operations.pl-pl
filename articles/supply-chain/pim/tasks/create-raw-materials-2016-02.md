---
title: Tworzenie surowców (luty 2016)
description: To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "351063"
---
# <a name="create-raw-materials-february-2016"></a>Tworzenie surowców (luty 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

To zadanie koncentruje się na tworzeniu składników wyrobów gotowych i półproduktów. Jest to trzecie zadanie w serii zadań obliczania BOM. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.


## <a name="create-the-first-material"></a>Tworzenie pierwszego materiału
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Kliknij przycisk Nowy.
3. W polu Numer produktu wpisz wartość.
    * W tym przykładzie wpisz ITEM_A.  
4. W polu grupa modelu produktu wpisz lub wprowadź wartość.
    * Wybierz opcję STD. STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.  
5. W polu Grupa towarów wprowadź lub wybierz wartość.
    * Na przykład zaznacz pozycję Dźwięk. To nie ma wpływu na obliczenia kosztów.  
6. W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.
    * Zaznacz pozycję SiteWH. W demonstracji będą wykorzystywane tylko oddział i magazyn.  
7. W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.
    * Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.  
8. Kliknij przycisk OK.
9. W okienku akcji kliknij pozycję Zarządzaj zapasami.
10. Kliknij opcję Ustawienia domyślne zamówień.
11. W polu Oddział zakupu wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
12. W polu Oddział zapasów wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
13. W polu Oddział sprzedaży wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
14. Zamknij stronę.
15. Zamknij stronę.
16. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij pozycję ITEM_A.  
17. Rozwiń sekcję Zarządzanie kosztami.
18. W polu Grupa kosztów wpisz wartość.
    * W tym przykładzie wpisz M2.  
19. W okienku akcji kliknij pozycję Zarządzanie kosztami.
20. Kliknij opcję Cena pozycji.
21. Kliknij przycisk Nowy.
22. W polu Wersja wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz wartość 10, która odpowiada typowi wyceny Koszt standardowy.  
23. W polu Oddział wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
24. W polu Cena wpisz liczbę.
    * W tym przykładzie wpisz wartość 10.  
25. Kliknij przycisk Zapisz.
26. Kliknij opcję Aktywuj oczekujące ceny.
27. Zamknij stronę.
28. Zamknij stronę.

## <a name="create-the-second-material"></a>Tworzenie drugiego materiału
1. Kliknij przycisk Nowy.
2. W polu Numer produktu wpisz wartość.
    * W tym przykładzie wpisz ITEM_B.  
3. W polu grupa modelu produktu wpisz lub wprowadź wartość.
    * Wybierz opcję STD. STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.  
4. W polu Grupa towarów wprowadź lub wybierz wartość.
    * Na przykład zaznacz pozycję Dźwięk. To nie ma wpływu na obliczenia kosztów.  
5. W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.
    * Zaznacz pozycję SiteWH. W tym przykładzie będą wykorzystywane tylko oddział i magazyn.  
6. W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.
    * Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.  
7. Kliknij przycisk OK.
8. W okienku akcji kliknij pozycję Zarządzaj zapasami.
9. Kliknij opcję Ustawienia domyślne zamówień.
10. W polu Oddział zakupu wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
11. W polu Oddział zapasów wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
12. W polu Oddział sprzedaży wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
13. Zamknij stronę.
14. Zamknij stronę.
15. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij pozycję ITEM_B.  
16. Rozwiń sekcję Zarządzanie kosztami.
17. W polu Grupa kosztów wpisz wartość.
    * W tym przykładzie wpisz M2.  
18. W okienku akcji kliknij pozycję Zarządzanie kosztami.
19. Kliknij opcję Cena pozycji.
20. Kliknij przycisk Nowy.
21. W polu Wersja wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję 10. Jest to typ wyceny Koszt standardowy.  
22. W polu Oddział wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
23. W polu Cena wpisz liczbę.
    * Dla demonstracji wpisz wartość 10.  
24. Kliknij przycisk Zapisz.
25. Kliknij opcję Aktywuj oczekujące ceny.
26. Zamknij stronę.
27. Zamknij stronę.

## <a name="create-the-third-material"></a>Tworzenie trzeciego materiału
1. Kliknij przycisk Nowy.
2. W polu Numer produktu wpisz wartość.
    * Dla demonstracji wpisz ITEM_C.  
3. W polu grupa modelu produktu wpisz lub wprowadź wartość.
    * Wybierz opcję STD. STD oznacza „koszt standardowy” i jest najczęściej używanym modelem podczas pracy z obliczeniami kosztów.  
4. W polu Grupa towarów wprowadź lub wybierz wartość.
    * Na przykład zaznacz pozycję Dźwięk. To nie ma wpływu na obliczenia kosztów.  
5. W polu grupa wymiaru magazynowania wpisz lub wprowadź wartość.
    * Zaznacz pozycję SiteWH. W demonstracji będą wykorzystywane tylko oddział i magazyn.  
6. W polu grupa wymiaru śledzenia wpisz lub wprowadź wartość.
    * Wymiary śledzenia nie będą używane w tym przykładzie. Wybierz opcję Brak.  
7. Kliknij przycisk OK.
8. W okienku akcji kliknij pozycję Zarządzaj zapasami.
9. Kliknij opcję Ustawienia domyślne zamówień.
10. W polu Oddział zakupu wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
11. W polu Oddział zapasów wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
12. W polu Oddział sprzedaży wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
13. Zamknij stronę.
14. Zamknij stronę.
15. Na liście kliknij łącze w wybranym wierszu.
    * Kliknij pozycję ITEM_C.  
16. Rozwiń sekcję Zarządzanie kosztami.
17. W polu Grupa kosztów wpisz wartość.
    * W tym przykładzie wpisz M1.  
18. W okienku akcji kliknij pozycję Zarządzanie kosztami.
19. Kliknij opcję Cena pozycji.
20. Kliknij przycisk Nowy.
21. W polu Wersja wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję 10. Jest to typ wyceny Koszt standardowy.  
22. W polu Oddział wprowadź lub wybierz wartość.
    * W tym przykładzie wybierz opcję Oddział 1.  
23. W polu Cena wpisz liczbę.
    * W tym przykładzie wpisz wartość 10.  
24. Kliknij przycisk Zapisz.
25. Kliknij opcję Aktywuj oczekujące ceny.
26. Zamknij stronę.
27. Zamknij stronę.

