---
title: Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu
description: W tym artykule zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy.
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2bb4115a486fbfe7287c9b183224699de4dfd456
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335534"
---
# <a name="ship-sales-orders-without-warehousing"></a>Wysyłanie towarów z zamówień sprzedaży bez przekazywania do magazynu

[!include [banner](../../includes/banner.md)]

W tym artykule zilustrowano sposób aktualizacji zamówienia sprzedaży, gdy produkty są wysyłane do odbiorcy. Przewodnik ma zastosowanie do przepływu realizacji, który nie jest skonfigurowany dla procesów zarządzania magazynem (WMS), a zatem nie wymaga, aby przed wysyłką zostało zarejestrowane pobranie produktu. Można wykonać tę procedurę przy użyciu danych własnych lub firmy demonstracyjnej USMF. W obu przypadkach przed rozpoczęciem tego zadania utwórz zamówienie sprzedaży na produkty magazynowe z ilością większą od 1. Aby uniknąć błędu księgowania, należy sprawdzić, czy ilość dostępnych zapasów produktu w oddziale i magazynie wybranych w zamówieniu pokrywa ilość zamówienia.

## <a name="post-packing-slip-for-an-order"></a>Księgowanie dokumentu dostawy dla zamówienia
1. W okienku nawigacji przejdź do **Moduły > Sprzedaż i marketing >Wszystkie zamówienia sprzedaży**.
2. Na liście znajdź i zaznacz zamówienie utworzone dla tego zadania.
3. W okienku akcji kliknij opcję **Pobierz i zapakuj**.
4. Wybierz **Księguj dokument dostawy**.
5. Rozwiń lub zwiń sekcję **Parametry**.
6. W polu **Ilość** zaznacz opcję **Wszystko**.
    - Inne dostępne opcje to **Dostawa teraz** i **Pobrane**. Jeśli towary z wiersza zamówienia mają zostać wysłane częściowo, a w wierszu zamówienia pole **Dostawa teraz** zawiera ilość, należałoby zaznaczyć opcję **Dostawa teraz**. Jeśli przepływ realizacji w firmie obejmuje pobranie jako oddzielny proces zarządzany i rejestrowany za pomocą listy pobrania, należałoby wybrać opcję **Pobrane**.  
    - Sprawdź, czy w opcji **Księgowanie** jest ustawiona wartość **Tak**.  
7. W opcji **Drukowanie dokumentu dostawy** zaznacz wartość **Tak**. Karta **Przegląd** zawiera listę dokumentów dostawy, jakie mają zostać wygenerowane w tym księgowaniu. Jeśli wysyłasz towary z jednego zamówienia, zwykle będzie jeden dokument dostawy. Jeśli jednak wiersze tego zamówienia mają być wysyłane z różnych oddziałów, księgowanie będzie automatycznie dzielone na odpowiednią liczbę dokumentów. To jest obowiązkowy warunek, którego nie można zmieniać. Podobnie księgowanie zostanie podzielone na wiele dokumentów, jeśli wiersze zamówienia mają zostać wysłane pod różne adresy dostawy, a zasady wysyłki określają wymaganie podziału.  
8. Na karcie **Wiersze** zaznacz wiersz dla wiersza zamówienia, który ma zostać wysłany.
9. W polu **Aktualizacja** wprowadź liczbę mniejszą niż ilość oryginalna.
10. Kliknij przycisk **OK**.
11. Wybierz opcję **Tak**.
12. Zamknij stronę.
13. W okienku akcji kliknij pozycję **Opcje**.
14. Wybierz **Zmień widok**.
15. Wybierz **Widok nagłówka**.
    - Gdy wszystkie wiersze zamówienia zostaną całkowicie wydane, stan zamówienia zmienia się z Otwarte na Dostarczone.  
    - W tym przykładzie wiersz zamówienia został wysłany częściowo. Dlatego zamówienie pozostaje w stanie Otwarte.     
    - W polu **Stan dokumentu** jest ustawiona wartość Dokument dostawy, ponieważ co najmniej jeden wiersz zamówienia został wysłany.  
16. W okienku akcji wybierz pozycję **Ogólne**.
17. Wybierz **Ilość w wierszu**.
18. Zamknij stronę.
19. W okienku akcji kliknij opcję **Pobierz i zapakuj**.
20. Wybierz **Dokument dostawy**. Strona **Arkusz dokumentu dostawy** zawiera wszystkie dokumenty dostawy, które zostały wygenerowane dla zamówienia. W razie potrzeby można przejrzeć szczegóły każdego dokumentu i je wydrukować.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]