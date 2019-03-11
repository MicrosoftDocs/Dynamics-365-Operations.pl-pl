---
title: Tworzenie zamówień sprzedaży
description: W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8af0333d979ba3a4e12d4f22b1225f3b72d66a7a
ms.sourcegitcommit: 2ebea3cbddfa0a5ef0e0fd13d3693da6152bc288
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "352121"
---
# <a name="create-sales-orders"></a>Tworzenie zamówień sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia zamówienia sprzedaży. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Zamówienia sprzedaży są zwykle tworzone przez agenta rozliczeniowego zamówień sprzedaży. 




## <a name="enter-sales-order-header-details"></a>Wprowadzanie szczegółów nagłówka zamówienia sprzedaży
1. Wybierz kolejno opcje Sprzedaż i marketing > Zamówienia sprzedaży > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz rekord odbiorcy.
    * W tym przykładzie należy wybrać numer odbiorcy US-004.  
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij przycisk OK.

## <a name="enter-sales-order-line-details"></a>Wprowadzanie szczegółów wiersza zamówienia sprzedaży
    * Produkty sprzedawane przez organizację mogą występować w wariantach zróżnicowanych według wymiarów, takich jak konfiguracja, kolor, rozmiar i styl. Ponadto konfiguracja produktów może określać używanie wymiarów magazynowania, takich jak oddział, magazyn i paleta, oraz wymiarów śledzenia, takich jak numery partii i numery seryjne. Po przypisaniu tych wymiarów należy wybierać ich wartości w wierszu zamówienia. Aby zwiększyć efektywność wprowadzania zamówień, warto dodać pola odpowiednich wymiarów do siatki zamówień.  
1. Kliknij wiersz Zamówienie sprzedaży.
2. Kliknij opcję Wymiary.
    * W tym przykładzie należy wybrać wymiary Kolor, Oddział i Magazyn. Wybrane tutaj wymiary będą wyświetlane w siatce zamówień sprzedaży. Jeśli chcesz utrwalić wybrane opcje, w ustawieniu Zapisz ustawienia zaznacz wartość Tak.   
3. Kliknij przycisk OK.
4. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. W tym przykładzie zaznacz numer towaru T0004.
6. Na liście kliknij łącze w wybranym wierszu.
    * Jeśli towar jest częścią kategorii sprzedaży, nazwa towaru będzie automatycznie wyświetlana w polu Kategoria sprzedaży.  
    * Jeśli pole wymiaru produktu już zawiera wartość, wynika to z tego, że wartość została skopiowana z rekordu produktu, gdzie jest zdefiniowana jako domyślny wymiar produktu. Wartość domyślną można w każdej chwili zmienić.   
7. W polu Kolor kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. Na liście kliknij łącze w wybranym wierszu.
10. Wprowadź liczbę w polu Ilość.
    * Jeśli towar jest sprzedawany w jednostkach innych niż w jakich był kupiony, wyprodukowany i przechowywany, a w rekordzie produktu ustawiono jednostkę miary sprzedaży, ta wartość będzie wyświetlana w polu Jednostka. Wartość można zmienić w dowolnym momencie.   
    * Jeśli pole Oddział już zawiera wartość, została ona skopiowana z nagłówka zamówienia lub z ustawień zamówienia skojarzonych z produktem. Wartość można zmienić w dowolnym momencie. Jeśli pole jest puste, wprowadź wartość.   
    * Jeżeli pole Cena jednostkowa już zawiera wartość, została ona skopiowana z obowiązującej umowy handlowej lub z rekordu produktu. (Cena jednostkowa może także pochodzić z umowy sprzedaży, ale proces tworzenia zamówień sprzedaży na podstawie umów sprzedaży różni się od pokazanego tutaj). Jeśli pole jest puste, wprowadź wartość.   
    * Pole Rabat zawiera kwotę rabatu na jednostkę produktu. Aby obliczyć kwotę rabatu dla łącznej wartości wiersza, wartość rabatu jest mnożona przez ilość w wierszu.    Jeżeli pole Rabat już zawiera wartość, została ona skopiowana z obowiązującej umowy handlowej. Jeśli pole jest puste, a chcesz przyznać odbiorcy rabat od wiersza, wprowadź wartość.  
    * Pole Procent rabatu zawiera wartość procentową, o jaką łączna kwota brutto w wierszu ma zostać pomniejszona.  Jeżeli pole Procent rabatu już zawiera wartość, została ona skopiowana z obowiązującej umowy handlowej. Jeśli pole jest puste, a chcesz przyznać odbiorcy rabat od wiersza, wprowadź wartość.  
    * Pole Kwota netto zawiera wartość, która jest obliczana na podstawie ilość w wierszu i ceny jednostkowej skorygowanej o rabaty.  Obliczoną wartość można samodzielnie zastąpić inną.  

## <a name="review-the-order-totals"></a>Przegląd sum zamówienia
1. W okienku akcji kliknij opcję Zamówienie sprzedaży.
2. Kliknij przycisk Sumy.
    * Na stronie Sumy są wyświetlane informacje dotyczące całego zamówienia. Obejmuje to kwotę sumy częściowej, czyli sumę wszystkich kwot netto z wierszy skorygowaną o ewentualne rabaty do wierszy, łączną kwotę faktury, czyli kwota sumy częściowej skorygowaną o ewentualne rabaty na poziomie zamówienia, opłaty, podatek, ewentualne limity kredytowe przyznane odbiorcy, itd.  Kwota faktury jest kwotą, która pojawi się w dokumencie faktury wystawionej odbiorcy.  
3. Kliknij przycisk OK.

