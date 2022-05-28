---
title: Obliczanie TDS dla faktur przy użyciu arkuszy
description: W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla arkuszy.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7f98caf92c49c229a11dd29d54e22106329e2401
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711360"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Obliczanie TDS dla faktur przy użyciu arkuszy

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla arkuszy.

Otwórz **Księga główna** (**Księga główna > Wpisy w arkuszu > Arkusze finansowe**).

[![Arkusze finansowe.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Umożliwia tworzenie wierszy arkusza przy użyciu formularzy arkusza wymienionych w tabeli. Wybierz typ konta i typ konta przeciwstawowego oraz wprowadź kwotę transakcji. 

   > [!NOTE]
   > Na stronie **Arkusz zatwierdzania faktur** wybierz pozycję **Znajdź załączniki i wybierz faktury**, dla których mają być obliczana wartość TDS. Wyświetlanie faktur utworzonych na stronie **Rejestr faktur** lub na stronie **Znajdowanie załączników**.  

2. Na karcie **Ogólne**, na stronie **Załącznik arkusza** w polu **Grupy TDS** przejrzyj lub zmień domyślną grupę TDS zdefiniowaną dla dostawcy lub odbiorcy. Kwota podatku potrącanego u źródła, która jest obliczana w wierszach arkusza, jest oparta na formule zdefiniowanej dla kodów podatku potrąconego podatku u źródła wymienionych w polu **Grupa potrącenia podatku u źródła**. 

   > [!NOTE]
   > Pole **Grupa podatku u źródła** i pole **Grupa TCS** stają się niedostępne po wybraniu grupy podatku u źródła w polu **Grupa podatku u źródła**. Pole **Grupa potrąconej zaliczki na podatek** jest dostępne tylko na **stronie arkusza ogólnego**. TDS jest obliczany tylko wtedy, gdy pole wyboru **Oblicz zaliczkę na podatek** jest zaznaczone dla dostawcy lub odbiorcy na stronie **Wszyscy dostawcy** lub **Wszyscy odbiorcy**.   

3. Wybierz kartę **Informacje podatkowe**. W razie potrzeby wybierz w tym polu alternatywne adresy firmy, która została skonfigurowana dla firmy. Nazwa firmy jest wyświetlana w polu **Nazwa**, które znajduje się w grupie **pól Informacje o firmie**. 

4. Wyświetl rodzaj kategorii osoby oceniającej dostawcy lub klienta w polu **Rodzaj osoby oceniającej**, które znajduje się w grupie pól **Podatek u źródła**. W polu **Numer konta podatkowego** (**TAN**) jest wyświetlany numer TAN wybranej nazwy firmy.  

5. Wybierz przycisk **Potrącona zaliczka na podatek** w meny **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**. Wyświetl następujące pola w górnym okienku strony **Tymczasowe transakcje potrącenia zaliczki na podatek**.

   - **Łączna kwota potrąconej zaliczki na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.

   - **Wartość** - łączna wartość procentowa użyta do obliczenia TDS dla transakcji. Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.

   - **Skorygowana łączna kwota potrąconej zaliczki na podatek** - łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.

   - **TDS** — jeśli ta opcja jest zaznaczona, do transakcji jest dołączona grupa TDS.

  Pola na kartach **Przegląd**, **Ogólne** i **Korekta** na stronie **Tymczasowe transakcje potrącenia zaliczki na podatek** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.

6. Wybierz **pozycję Próg**, aby otworzyć stronę **Próg**. Umożliwia wyświetlenie na tej stronie limitu progowego zdefiniowanego dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.

   Wybierz opcję **Projektant formuł**, aby otworzyć formularz **Projektant formuł**. Na tej stronie można wyświetlić formułę zdefiniowaną dla określonego kodu podatku TDS. Zamknij strony **Konstruktor formuł** i **Tymczasowe transakcje potrącenia zaliczki na podatek**, aby powrócić do **strony załącznika arkusza**.

8. Wprowadź wymagane dane. Sprawdź poprawność arkusza i zaksięguj go. Kwota TDS obliczona na fakturach zakupu jest księgowana na koncie rozrachunków z dostawcami. Kwota podatku potrącanego u źródła obliczona na fakturach sprzedaży jest księgowana na koncie należności zdefiniowanym dla każdego kodu podatku potrącanego u źródła w grupie podatku potrąconego u źródła. Konta rozrachunków lub należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.

9. Wybierz przycisk **Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **transakcje potrącenia zaliczki**. **Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.

   Pola na kartach **Przegląd**, **Ogólne** i **Kwota** na stronie Tymczasowe transakcje potrącenia zaliczki na podatek pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.
