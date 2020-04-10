---
title: Utworzenie konta dostawcy
description: W tej procedurze pokazano, jak utworzyć konto dostawcy oraz dodać informacje adresowe i kontaktowe.
author: mkirknel
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba585a9bb1a296bbf7181530e151d737bfa22fc2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149603"
---
# <a name="create-a-vendor-account"></a>Utworzenie konta dostawcy

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak utworzyć konto dostawcy oraz dodać informacje adresowe i kontaktowe. Procedura nie pokazuje sposobu wypełnienia wszystkich pól do celów zakupowych i finansowych. Aby uzyskać więcej informacji o tych polach, przeczytaj ich opisy. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Konta dostawców są zwykle tworzone przez pracownika działu zaopatrzenia lub personel działu rozrachunków z odbiorcami.


## <a name="create-a-vendor-account"></a>Tworzenie konta dostawcy
1. Przejdź do **Okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.**
2. Kliknij przycisk **Nowy**.
3. W polu **Konto dostawcy** wpisz wartość.
    - Wartość może być wprowadzana automatycznie. Jeśli tak się dzieje, możesz pominąć ten krok.  
    - Można tworzyć konta dostawców dla osób lub organizacji. Wpłynie to na dostępność pól. W tym przykładzie utworzymy konto dostawcy dla organizacji.   
4. W polu **Nazwa** wprowadź lub wybierz wartość. Jeśli dostawca jest już stroną zarejestrowaną w systemie, można użyć listy rozwijanej i zaznaczyć go w tym polu, a nowe konto dostawcy odziedziczy już zarejestrowane informacje adresowe i kontaktowe.
5. W polu **Grupa** wprowadź lub wybierz wartość. Grupa dostawców jest używana do grupowania dostawców, którzy mają wspólny dowolny z następujących parametrów: warunki płatności, rozliczenie okresu, konta księgowe księgowania zapasów (łącznie z grupą podatków), domyślne konta księgowe, kody filtrów produktów lub konfiguracja prognoz dostaw.
6. W polu **Liczba pracowników** wprowadź liczbę.
7. W polu **Numer organizacji** wpisz wartość.

## <a name="add-an-address"></a>Dodawanie adresu
1. Rozwiń sekcję **Adresy**.
2. Kliknij przycisk **Dodaj**.
3. W polu **Cel** wprowadź lub wybierz wartość. Można wybrać jeden lub więcej celów. Są one używane do wybierania poprawnego adresu dla danego celu. Na przykład jeśli celem jest „Faktura”, ten adres będzie używany przy wysyłaniu faktur.
4. W polu **Nazwa lub opis** wpisz wartość.
5. W polu **Kraj/region** wprowadź lub wybierz wartość. Podaj szczegóły adresu. Wybrany kraj/region zdecyduje o polach, które zostaną Ci wyświetlone, stosownie do formatu adresu kraju/regionu. 
6. Kliknij przycisk **OK**.

## <a name="add-contact-information"></a>Dodawanie informacji kontaktowych
1. Rozwiń sekcję **Informacje kontaktowe**.
2. Kliknij przycisk **Dodaj**.
3. W polu **Opis** wpisz wartość.
4. W polu **Typ** wybierz opcję.
5. W polu **Numer/adres osoby kontaktowej** wpisz wartość. Jeśli jest to podstawowa osoba kontaktowa, można zaznaczyć pole wyboru Podstawowe.  
6. Kliknij przycisk **Zapisz**.
7. Zamknij stronę.
8. Zamknij stronę.

