---
title: Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży
description: Ta procedura pokazuje, jak utworzyć zamówienie zakupu oparte na zamówieniu sprzedaży.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5d7ce50532fb5bd6723b783d96d756085142e10
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843392"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak utworzyć zamówienie zakupu oparte na zamówieniu sprzedaży. Ilości produktów w zamówieniu zakupu są następnie przeznaczane do zaspokojenia zapotrzebowania w źródłowym zamówieniu sprzedaży. Ten sposób realizacji zapotrzebowania sprzedaży stanowi alternatywę dla bardziej kompleksowej i zoptymalizowanej metody Planowanie wymagań dystrybucji. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Kliknij przycisk OK.
6. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz firmy USMF, można wybrać towar D0001.  
8. Wprowadź liczbę w polu Ilość.
9. Kliknij przycisk Dodaj wiersz.
10. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz firmy USMF, można wybrać towar T0020.  
12. Na liście kliknij łącze w wybranym wierszu.
13. Wprowadź liczbę w polu Ilość.
14. Kliknij przycisk Zapisz.
15. W okienku akcji kliknij opcję Zamówienie sprzedaży.
16. Kliknij opcję Zamówienie zakupu.
    * Strona Tworzenie zamówienia zakupu zawiera listę wszystkich otwartych wierszy zamówienia sprzedaży, które zostały skopiowane z zamówienia sprzedaży. Przed utworzeniem zakupów można przejrzeć szczegóły zamówienia i w razie potrzeby zmodyfikować wybrane szczegóły, takie jak ilość zakupu i warunki cenowe.  
17. Zaznacz opcję Uwzględnij wszystko.
    * Jeśli chcesz wygenerować zamówienia zakupu tylko dla podzbioru wierszy zamówienia sprzedaży, wybierz je pojedynczo.  
    * Pole Konto dostawcy może, ale nie musi, być już wypełnione numerem dostawcy. Jeśli dla produktu jest zdefiniowany dostawca domyślny (w powiązanym zapotrzebowaniu na towar), ten dostawca zostanie skopiowany do wiersza. W przeciwnym razie dostawcę należy wprowadzić ręcznie.  W tym przewodniku bez względu na to, czy pole Konto dostawcy już zawiera wartość, w kolejnych krokach znajdzie się instrukcja wybrania nowego dostawcy innego dla każdego wiersza.  
18. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
19. Na liście znajdź i zaznacz odpowiedni rekord.
20. Na liście kliknij łącze w wybranym wierszu.
21. Zaznacz drugi wiersz zamówienia.
22. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
23. Na liście znajdź i zaznacz odpowiedni rekord.
24. Na liście kliknij łącze w wybranym wierszu.
25. Kliknij przycisk Sprawdź poprawność.
26. Kliknij przycisk OK.
    * Komunikat informuje, że utworzono co najmniej jedno zamówienie zakupu. System generuje osobne zamówienie zakupu dla każdego dostawcy określonego dla wierszy zamówienia sprzedaży. Oznacza to, że jeśli towary do kilku wierszy zamówienia sprzedaży mają być dostarczane przez tego samego dostawcę, zostanie wygenerowane jedno zamówienie zakupu z wieloma wierszami.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Przegląd zamówień zakupu utworzonych na podstawie zamówień sprzedaży
1. W okienku akcji kliknij pozycję Ogólne.
2. Kliknij opcję Powiązane zamówienia.
    * Na stronie Powiązane zamówienia znajduje się lista wszystkich zamówień, które zostały utworzone na podstawie zamówienia sprzedaży. W tym przykładzie istnieją dwa zamówienia zakupu wygenerowane dla dwóch różnych dostawców.  
3. Kliknij, aby śledzić łącze w polu Zamówienie zakupu.
    * Każdy wiersz zamówienia zakupu jest skojarzony z wierszem zamówienia sprzedaży, które doprowadziło do zakupu. Powiązanie z zamówieniem sprzedaży jest wskazane na karcie Produkt na skróconej karcie Szczegóły wiersza w polach Typ odwołania, Numer odwołania i Partia odwołań.  
4. Rozwiń lub zwiń sekcję Szczegóły wiersza.
5. Kliknij kartę Produkt.
    * Opcja Partia odwołań gwarantuje, że koszty z bieżącego zakupu obciążą dołączone zamówienie sprzedaży.  
    * Aby przejść do źródłowego zamówienia sprzedaży, można otworzyć łącze znajdujące się w polu Numer odwołania.  

