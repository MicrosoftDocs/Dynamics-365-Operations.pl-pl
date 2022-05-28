---
title: Obliczanie faktur TDS przy użyciu formularza zamówienia zakupu i formularza zamówienia sprzedaży
description: W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) dla różnych typów faktur.
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
ms.openlocfilehash: 6a7e670c38a1bce6b8f6771b4be49e56e3aa785a
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711956"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Obliczanie faktur TDS przy użyciu formularza zamówienia zakupu i formularza zamówienia sprzedaży

[!include [banner](../includes/banner.md)]

W tym temacie wymieniono kroki obliczania podatku potrąconego w źródle (TDS) na różnych typach faktur przy użyciu stron **Zamówienie zakupu**, **Arkusz zakupów**, **Zamówienie zbiorcze** i **Zamówienie sprzedaży**.

1. Strona ta umożliwia tworzenie zamówienia zakupu, arkusza zakupu, zbiorczego zamówienia zakupu lub zamówienia sprzedaży. Wprowadź wymagane informacje.

2. Wybierz **kartę Ustawienia**, aby wyświetlić charakter oceny dostawcy lub odbiorcy. Te informacje są wymienione w polu **Charakter oceny** w grupie pól **Grupa potrąconej zaliczki na podatek**.

3. W polu **Grupa TDS** wyświetl lub zmodyfikuj domyślną grupę TDS zdefiniowaną dla dostawcy lub odbiorcy.

   > [!NOTE]
   > Pole **grupa TCS** nie jest dostępne po wybraniu grupy TDS w polu **grupa TCS**. TDS jest obliczany tylko wtedy, gdy pole wyboru **Oblicz zaliczkę na podatek** jest zaznaczone dla dostawcy lub odbiorcy na stronie **Wszyscy dostawcy** lub **Wszyscy odbiorcy**.  

4. Na karcie **Wiersze faktury** utwórz pozycje pozycji w dniu i wprowadź wymagane szczegóły.

5. Wybierz **kartę Ustawienia** (poziom wiersza), aby wyświetlić lub zmienić grupę TDS zdefiniowaną na poziomie nagłówka. Grupa TDS jest wyświetlana w polu **Grupa TDS**, które znajduje się w grupie pól **Grupa potrąconej zaliczki na podatek**.

6. Wybierz kartę **Informacje podatkowe** i wybierz adresy alternatywne ustawione dla nazwy firmy wyświetlanej w tym polu. Nazwa firmy jest wyświetlana w polu **Nazwa**, które znajduje się w grupie **pól Informacje o firmie**. 

   Numer IDENTYFIKACYJNY wybranej nazwy firmy jest wyświetlany w polu **Numer konta podatkowego (**TAN**)** w grupie pól **Potrącona zaliczka na podatek**. 

7. Wybierz przycisk **Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**. Wyświetl następujące pola w górnym okienku strony **Tymczasowe transakcje potrącenia zaliczki na podatek**.

   - **Łączna** **kwota** **potrąconej** **zaliczki** **na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.

   - **Wartość** - łączna wartość procentowa użyta do obliczenia TDS dla transakcji. Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.

   - **Skorygowana łączna kwota potrąconej zaliczki na podatek** - łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.

   - **TDS** — jeśli ta opcja jest zaznaczona, do transakcji jest dołączona grupa TDS.

Pola na kartach **Przegląd**, **Ogólne** i **Korekta** na stronie **Tymczasowe transakcje potrącenia zaliczki na podatek** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.

8. Wybierz **pozycję Próg**, aby otworzyć stronę **Próg**. Umożliwia wyświetlenie na tej stronie limitu progowego zdefiniowanego dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.

9. Wybierz opcję **Projektant formuł**, aby otworzyć stronę **Projektant formuł**. Na tej stronie można wyświetlić formułę zdefiniowaną dla określonego kodu podatku TDS. 

10. Zaksięguj fakturę. Kwota TDS obliczona na fakturach zakupu jest księgowana na koncie zobowiązań, a kwota TDS obliczona na fakturach sprzedaży jest księgowana na koncie należności określonym dla każdego kodu podatku TDS w grupie TDS. Konta rozrachunków lub należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.

11. Wybierz przycisk **Zapytanie** **> Faktura > Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **Transakcje potrącenia zaliczki**. Pole **Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.

W polach na kartach **Przegląd**, **Ogólne** i **Kwota** na stronie **Transakcje potrącenia zaliczki na podatek** są wyświetlane informacje o identyfikatorze TDS obliczonym dla transakcji. Zobacz informacje o obliczaniu TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.
