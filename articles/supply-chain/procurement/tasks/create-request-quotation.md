---
title: Tworzenie zapytania ofertowego
description: W tej procedurze pokazano sposób tworzenia zapytania ofertowego.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchCreateRFQCase, InventLocationIdLookup, PurchRFQCaseTable, InventItemIdLookupSimple, EcoResCategorySingleLookup, UnitOfMeasureLookup, PurchRFQEditLines, PurchRFQEditLinesPrintOptions, VendRFQJournal, SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68624a0288f9eaaf8f74b361bb308b8ca3c03b29
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435093"
---
# <a name="create-a-request-for-quotation"></a>Tworzenie zapytania ofertowego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia zapytania ofertowego. Zazwyczaj robi to pracownik działu zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Przed rozpoczęciem trzeba mieć skonfigurowane typy zdobywania zamówień. Po wykonaniu tego zadania i utworzeniu oraz wysłaniu ZO można wprowadzić odpowiedzi dla poszczególnych dostawców, porównać je, a następnie przyznać zamówienie.


## <a name="prepare-a-new-rfq"></a>Przygotowywanie nowego ZO
1. Wybierz kolejno **okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Zapytania ofertowe > Wszystkie zapytania ofertowe**.
2. Kliknij przycisk **Nowy**.
    Dostępne są następujące typy zakupu: Zamówienie zakupu (jest to ustawienie domyślne): dokument potwierdzający ofertę kupna produktów lub zaakceptowanie oferty sprzedaży produktów w zamian za płatność. Zapotrzebowanie na zakup: ten typ jest zaznaczany automatycznie, jeśli zapytanie ofertowe jest tworzone bezpośrednio na podstawie zapotrzebowania zakupu. W przypadku ręcznego zaznaczenia tej opcji pojawi się komunikat o błędzie. Umowa zakupu: umowa zakupu podanej ilości lub wartości produktu w określonym czasie. Jeśli zostanie wybrana ta opcja, należy wybrać zakres dat, który ma zastosowanie do umowy zakupu.  
3. W polu **Tytuł dokumentu** wpisz wartość.
4. W polu **Typ zdobywania zamówień** wprowadź lub wybierz wartość.
    + Jeśli z typem zdobywania zamówień jest skojarzona metoda punktowania, będzie to domyślna metoda punktowania dla tworzonego ZO. Później można zmienić metodę punktowania.  
    + W polu **Data dostawy** wpisz datę.  
    + Zaznacz datę, do kiedy chcesz otrzymać towary.  
    + W polu **Data i godzina ważności** wprowadź datę i godzinę.  
    + Określ datę i godzinę, do kiedy dostawca musi odpowiedzieć na ZO.  
5. W polu **Magazyn wprowadź** lub wybierz wartość. Adresem dostawy będzie domyślnie adres magazynu.  
6. Kliknij przycisk **OK**.

## <a name="add-lines"></a>Dodaj wiersze

Po określeniu podstawowych informacji o ZO, określ towary lub usługi, na które dostawcy mają złożyć oferty. Domyślnym typem wiersza jest Towar.

1. W polu **Kod towaru** wpisz lub wprowadź wartość. Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar T0020.  
2. W polu **Ilość** wpisz liczbę.
3. Kliknij przycisk **Dodaj wiersz.**
4. W polu **Typ wiersza** wybierz opcję „Kategoria”. Typ wiersza Kategoria może służyć do tworzenia ZO na pozamagazynowe towary lub usługi. Następnie należy wybrać rodzaj towarów lub usług z hierarchii kategorii zaopatrzenia.  
5. W polu **Kategoria zaopatrzenia** wprowadź lub wybierz wartość.
6. W polu **Nazwa produktu** wpisz wartość.
7. W polu **Ilość** wpisz liczbę.
8. W polu **Jednostka** wprowadź lub wybierz wartość.

## <a name="add-vendors"></a>Dodawanie dostawców
1. Kliknij **Nagłówek** i zmień widok z widoku wierszy na widok nagłówka. 
2. Rozwiń sekcję **Dostawca**.
3. Kliknij opcję **Automatyczne dodawanie dostawców**. Można dodać dostawców do ZO automatycznie na podstawie kategorii zaopatrzenia zamówionych towarów. Jeśli nie ma dostawców zatwierdzonych dla kategorii zawartych w wierszach, można dodać dostawców ręcznie.  
4. Kliknij przycisk **Dodaj**.
5. W polu **Konto dostawcy** wprowadź lub wybierz wartość.
6. Kliknij przycisk **Dodaj**.
7. W polu **Konto dostawcy** wprowadź lub wybierz wartość. Po zaznaczeniu dostawcy jego stanem jest Utworzone. Oznacza to, że dane dostawcy zostały zapisane w zapytaniu ofertowym, jednak zapytania nie wysyłano do dostawcy. Można dodawać dostawcę do zapytania ofertowego niezależnie od stanu dostawcy.  

## <a name="send-the-rfq-to-vendors"></a>Wyślij ZO do dostawców
1. W **okienku akcji** kliknij pozycję **Wyślij**. Na stronie Wysyłanie zapytania ofertowego sprawdź, czy dostawcy na liście są tymi, którzy powinni otrzymać ZO.  
2. Kliknij przycisk **Drukuj**. To okno dialogowe umożliwia wydrukowanie ZO. Jeśli chcesz wydrukować arkusz odpowiedzi, jego zawartość należy zdefiniować w oknie Parametry modułu Zaopatrzenie i sourcing. Aby wybrać sposób drukowania arkuszy odpowiedzi, po otwarciu okna dialogowego Drukowanie kliknij przycisk Zaawansowane opcje drukowania. Zostanie wydrukowane jedno ZO dla każdego dostawcy zawierającego wiersze o stanie Utworzone lub Wysłane. Wiersze anulowane i wiersze z zarejestrowanymi odpowiedziami nie są drukowane.   
3. Kliknij **Anuluj**.
4. Kliknij przycisk **OK**.
5. Zamknij stronę.
6. Zamknij stronę.

## <a name="view-the-rfq-journal"></a>Wyświetlanie arkusza ZO
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing > Zapytania ofertowe > Kolejne działania dotyczące zapytania ofertowego > Arkusze zapytań ofertowych**.
2. Kliknij opcję **Podgląd/drukuj**.
3. Kliknij opcję **Podgląd oryginału**.
4. Zamknij stronę.
5. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]