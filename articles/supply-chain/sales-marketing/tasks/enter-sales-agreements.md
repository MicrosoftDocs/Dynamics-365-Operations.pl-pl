--- 
title: "Wprowadzanie umów sprzedaży"
description: "W tej procedurze pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na ustaloną kwotę w określonym czasie w zamian za specjalne rabaty."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 8c11164f7edb8e05b93f3c58b9707c0bf2482228
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="enter-sales-agreements"></a>Wprowadzanie umów sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na

ustaloną kwotę w określonym czasie w zamian za specjalne rabaty. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-sales-agreement-header"></a>Konfigurowanie nagłówka umowy sprzedaży
1. Wybierz kolejno opcje Sprzedaż i marketing > Umowy sprzedaży > Umowy sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Na liście kliknij łącze w wybranym wierszu.
6. W polu Klasyfikacja umowy sprzedaży kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście kliknij łącze w wybranym wierszu.
8. Rozwiń sekcję Ogólne.
9. W polu Domyślne zobowiązanie wybierz opcję „Zobowiązanie co do wartości produktu”.
    * Typ zobowiązania to wymagane kryterium, które należy przypisać do umowy, aby zdefiniować sposób realizacji umowy. Cztery wstępnie zdefiniowane typy umożliwiają skonfigurowanie przedmiotu zobowiązania dla odbiorcy, wyrażonego jako ilość lub wartość. Zobowiązanie co do ilości można zastosować tylko do określonego produktu, ale typy oparte na wartości mają zastosowanie do sprzedaży produktów określonych i nieokreślonych.  
10. W polu Data wygaśnięcia ustaw przyszłą datę, kiedy umowa ma wygasnąć.
11. Kliknij przycisk OK.

## <a name="set-up-product-value-commitment-lines"></a>Konfigurowanie wierszy zobowiązania co do wartości produktu
1. Kliknij przycisk Dodaj wiersz.
2. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
    * Typ zobowiązania wybrany dla umowy wpływa na rodzaj informacji, które można wprowadzać w wierszach umowy. Na przykład w umowie opartej na wartości trzeba określić łączną kwotę netto (w uzgodnionej walucie), za którą odbiorca zobowiązuje się kupić towary od Twojej firmy. W tym przykładzie pola Ilość i Jednostka w wierszu są niedostępne, ponieważ tworzysz umowę dotycząca kupna produktów na określoną wartość przez odbiorcę.   
5. W polu Kwota netto wprowadź kwotę pieniężną, za jaką odbiorca zobowiązał się kupić.
6. W polu Procent rabatu wprowadź wartość procentową, która będzie stosowana do wierszy zamówienia sprzedaży odbiorcy połączonych z tą umową.
7. Rozwiń sekcję Szczegóły wiersza.
8. W polu Wymuszono maks. wybierz opcję Tak.
    * Wybór opcji Wymuszono maks. oznacza, że łączna ilość we wszystkich wierszach zamówienia sprzedaży, które używają specjalnych cen, rabatów i/lub warunków płatności zobowiązania, nie może przekraczać kwoty określonej w zobowiązaniu.  
    * Kwoty zwolnienia minimalna i maksymalna określają zakres wartości, na które należy wykonać sprzedaż w każdym zamówieniu sprzedaży korzystającym z wybranej umowy.   
9. Rozwiń sekcję Nagłówek umowy sprzedaży.
    * Jeśli umowa ma stan inny niż Obowiązuje, zamówienia sprzedaży nie mogą być kojarzone z umową i w związku z tym nie mogą się przyczyniać do realizacji umowy. Stan można zmienić ręcznie na tym etapie. Jednak stan zazwyczaj zmienia się podczas potwierdzania umowy dla odbiorcy.  
10. W okienku akcji kliknij opcję Umowa sprzedaży.
11. Kliknij opcję Potwierdzenie.
    * Upewnij się, że w opcji Oznaczenie umowy jako obowiązującej zaznaczono wartość Tak.  
12. W polu Drukuj raport zaznacz opcję Tak.
13. Kliknij przycisk OK.
14. Zamknij stronę.
    * Umowa teraz obowiązuje i można rozpocząć łączenie zamówień odbiorcy z umową w celu umożliwienia realizacji zadeklarowanego celu zakupowego.  


