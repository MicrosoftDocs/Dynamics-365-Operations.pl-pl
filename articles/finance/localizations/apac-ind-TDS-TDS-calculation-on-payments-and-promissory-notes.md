---
title: Obliczanie TDS dla płatności i skryptów dłużnych
description: Ten temat zawiera informacje referencyjne dotyczące różnych transakcji płatności, według których jest obliczany podatek potrącony w źródle (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d5c9822c2e4f71fb89776d1c1c76056bad85d484
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407668"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Obliczanie TDS dla płatności i skryptów dłużnych

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje referencyjne dotyczące różnych transakcji płatności, według których jest obliczany podatek potrącony w źródle (TDS).

| Numer seryjny | Typ transakcji | Kwota transakcji | Nazwa i ścieżka pliku | Typ konta i typ konta przeciwstawnego |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Płatność zaliczki/płatność za fakturę (TDS) | Debet czy Kredyt | <ul><li>Księga główna (**Księga główna \> Wpisy w arkuszu \> Arkusze finansowe**)</li><li>Arkusz faktury (**Rozrachunki z dostawcami \> Faktury \> Arkusz zatwierdzania faktur**)</li><li>Arkusz płatności (**Rozrachunki z dostawcami \> Płatności \> Arkusz płatności dostawcy**)</li></ul> | Dostawca (dr.), bank (Cr.) |
| 2             | Płatność zaliczkowa/płatność za fakturę (Zakup od odbiorcy — TDS zobowiązań) | Debet czy Kredyt | <ul><li>Księga główna (**Księga główna \> Wpisy w arkuszu \> Arkusze finansowe**)</li><li>Arkusz faktury (**Rozrachunki z dostawcami \> Faktury \> Arkusz zatwierdzania faktur**)</li><li>Arkusz płatności (**Rozrachunki z dostawcami \> Płatności \> Arkusz płatności dostawcy**)</li></ul> | Klient (dr.), bank (Cr.) |
| 3             | Skrypty dłużne | Uznanie | Arkusz draw skryptów dłużnych (**Rozrachunki z dostawcami \> Płatności \> Skrypt dłużny \> Arkusz wystawiania skryptów dłużnych**) | Dostawca (dr.), księga (Cr.) |
| 4             | Dochód różny (TDS, należności) | Debet czy Kredyt | Księga główna (**Księga główna \> Wpisy w arkuszu \> Arkusze finansowe**) | Bank (dr.), księga (Cr.) |
| 5             | Inne wydatki (TDS zobowiązań) | Debet czy Kredyt | Księga główna (**Księga główna \> Wpisy w arkuszu \> Arkusze finansowe**) | Bank (dr.), księga (Cr.) |

Aby obliczyć TDS dla płatności i skryptów dłużnych, należy wykonać następujące kroki.

1. Na stronach arkuszy utwórz wiersze arkusza. Wybierz typ konta i typ konta przeciwstawnego.
2. Wybierz **Funkcje \> Rozliczenie**, aby otworzyć stronę **edycji otwartej transakcji**. Następnie wybierz określoną fakturę, która ma zostać rozliczona. Jeśli identyfikator TDS został już obliczony na poziomie faktury, w polu Podstawa jest obliczana **kwota podstawowa**, na podstawie których został obliczony identyfikator TDS. Pole **Kwota podatku** pokazuje kwotę TDS obliczona dla transakcji. W polu **Kwota** jest kwota płatności netto (to jest kwota płatności po potrąceniu TDS).

    > [!NOTE]
    > W przypadku płatności dokonanej na fakturze mają zastosowanie następujące warunki:
    >
    > - Jeśli kwota płatności i kwota faktury są takie same, identyfikator TDS nie jest obliczany, jeśli został już obliczony na poziomie faktury.
    > - Jeśli kwota faktury po potrąceniu kwoty TDS jest wyższa niż kwota płatności, identyfikator TDS nie jest obliczany.
    > - Jeśli kwota faktury po potrąceniu kwoty TDS jest mniejsza niż kwota płatności, identyfikator TDS jest obliczany na podstawie kwoty przekraczającej kwotę faktury.

3. Na stronie **Załącznik arkusza**, na karcie **Przegląd** w polu **Grupy TDS** przejrzyj lub zmień domyślną grupę TDS zdefiniowaną dla dostawcy lub odbiorcy. Identyfikator TDS obliczany w wierszach arkusza jest oparty na formule zdefiniowanej dla kodów podatków TDS w grupie TDS.

    > [!NOTE]
    > Identyfikator TDS jest obliczany tylko wtedy, gdy opcja **Oblicz potrącanie zaliczki** na podatek ma wartość **Tak** dla dostawcy na stronie **Dostawcy**.

4. Na karcie **Informacje podatkowe**, w sekcji **Informacje o firmie**, w polu **Nazwa** można wybrać nazwę firmy dla adresów alternatywnych ustawionych dla firmy.

    W sekcji **Potrącona zaliczka** na podatek pole **Charakter grupy oszacowań** pokazuje charakter kategorii produktów ocenianych dostawcy lub odbiorcy. Pole **Numer rachunku podatkowego (TAN)** pokazuje numer rachunku podatkowego (TAN) wybranej firmy.

5. Wybierz przycisk **Potrącona zaliczka na podatek \> Potrącona zaliczka na podatek**, aby otworzyć stronę **Tymczasowe transakcje potrącenia zaliczki na podatek**. W górnej części tej strony są następujące pola:

    - **Łączna kwota potrąconej zaliczki na podatek** — łączna kwota TDS obliczona dla transakcji dla grupy TDS.
    - **Wartość** — łączna wartość procentowa użyta do obliczenia TDS dla transakcji. Łączny procent jest oparty na formule zdefiniowanej dla kodów podatków TDS i dołączonej do grupy TDS.
    - **Skorygowana łączna kwota potrąconej zaliczki na podatek** — łączna skorygowana kwota TDS dla wszystkich kodów podatków w grupie TDS.
    - **TDS** — zaznaczone pole wyboru wskazuje, że grupa TDS jest dołączona do transakcji.

    Pola na kartach **Przegląd**, **Ogólne** i **Korekta** pokazują obliczoną kwotę TDS oraz szczegóły skorygowanej kwoty TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.

6. Wybierz opcję **Próg**, aby otworzyć stronę **Progu**, na której możesz przejrzeć limit progowy zdefiniowany dla składnika podatku TDS dołączonego do określonego kodu podatku TDS.
7. Po wybraniu opcji **Projektant formuł** zostanie otwarta strona **Projektant formuł**, na której można przejrzeć formułę zdefiniowaną dla określonego kodu podatku TDS.
8. Zamknij strony **Konstruktor formuł** i **Tymczasowe transakcje potrącenia zaliczki na podatek**, aby powrócić do **strony załącznika arkusza**.
9. Sprawdź poprawność arkusza i zaksięguj go. Obliczona kwota TDS jest księgowana na koncie zobowiązań zdefiniowanym dla każdego kodu podatku TDS w grupie TDS. Konta należności dla kodów podatku TDS są definiowane na stronie **Kody potrąconych zaliczek na podatek**.
10. Wybierz przycisk **Zaksięgowana potrącona zaliczka na podatek**, aby otworzyć stronę **transakcje potrącenia zaliczki**. **Wartość** pokazuje łączną wartość procentowa użyta do obliczenia TDS dla transakcji.

    W polach na kartach **Przegląd**, **Ogólne** i **Kwota** są wyświetlane kwoty TDS, które zostały obliczone dla grupy TDS dołączonej do transakcji.

11. Przejrzyj informacje o obliczaniu TDS dla każdego kodu podatku TDS dołączonego do grupy TDS.

## <a name="generate-payments"></a>Generuj płatności

Aby wygenerować płatności, wykonaj następujące kroki.

1. Wykonaj jeden z następujących kroków:

    - Przejdź do pozycji **Rozrachunki z dostawcami \> Płatności \> Arkusz płatności dostawcy**.
    - Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Arkusz płatności klienta**.
    - Przejdź do **Rozrachunki z dostawcami \> Płatności \> Skrypt dłużny \> Arkusz wystawiania skryptów dłużnych**.
    - Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Weksel \> Arkusz wystawiania weksli**.
    - Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Weksel \> Arkusz ponownego wystawiania wekslil**.

2. Wybierz **Linie**.
3. Wybierz **Funkcje \> Generuj płatności**.
