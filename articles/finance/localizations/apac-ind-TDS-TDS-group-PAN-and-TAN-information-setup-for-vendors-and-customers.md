---
title: Skonfiguruj informacje o grupie TDS, PAN i TAN dla dostawców i klientów
description: W tym temacie wyjaśniono, jak skonfigurować informacje o grupie potrącanej z podatku w źródle (TDS), trwały numer konta (PAN) i numerze konta podatkowego (TAN) dla dostawców i odbiorców.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: b736838f1743a39d1f899f2679a31a2c0fe9a2b31e03b29d22af821314f329c9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745755"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>Skonfiguruj informacje o grupie TDS, PAN i TAN dla dostawców i klientów

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować informacje o grupie potrącanej z podatku w źródle (TDS), trwały numer konta (PAN) i numerze konta podatkowego (TAN) dla dostawców i odbiorców.

1. Przejdź do **Rozrachunki z dostawcami \> Dostawcy \> Wszyscy dostawcy** lub **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.

    [![Strona wszystkich dostawców.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. Wybierz **Nowy** na okienku akcji, aby utworzyć dostawcę lub odbiorcę, i wprowadź wymagane szczegóły. Możesz również wybrać istniejącego dostawcę lub dostawcę.
3. Na skróconej karcie **Faktura i dostawa**, w sekcji **Potrącona zaliczka na podatek**, aby **obliczyć potrąconą zaliczkę na podatek** ustaw wartość **Tak**, TDS lub podatek potrącony w źródle (TCS) dla dostawcy lub odbiorcy.
4. Identyfikator TDS faktury zakupu jest obliczany na podstawie domyślnej grupy TDS zdefiniowanej dla dostawcy lub odbiorcy. W polu **Grupa TDS** wybierz grupę TDS.

    > [!NOTE]
    > Po wybraniu grupy TDS w polu **Grupa TDS** pola **Grupa potrąconej zaliczki na podatek** i grupa **TCS** stają się niedostępne.

5. Na skróconej **karcie Informacje podatkowe**, w sekcji **Informacje PAN**, w polu **Stan** wybierz stan stałego numeru konta dla dostawcy lub odbiorcy:

    - **Niedostępny** — dostawca lub odbiorca nie ma konta PAN.
    - **Otrzymane** — dostawca lub odbiorca ma numer PAN.
    - **Zastosowane** — dostawca lub odbiorca złożył wniosek o PAN.
    - **Nieprawidłowy** — dostawca lub odbiorca ma numer PAN, ale jest nieprawidłowy.

6. Jeśli wybrano opcję **Odebrane** w polu **Stan**, aby wskazać, że dostawca lub odbiorca ma opcję PAN, w polu **Numer** wprowadź nazwę PAN. Znak PAN musi składać się z pięciu znaków alfabetycznych, czterech cyfr i jednego znaku alfabetycznego. Oto przykład: **ABCDE1260A**.
7. Jeśli wybrano opcję **Zastosowano** w polu **Stan**, aby wskazać, że dostawca lub odbiorca ma opcję PAN, w polu **Numer odnośnika** wprowadź numer odnośnika.
8. W polu **Rodzaj osoby oceniającej** wybierz rodzaj kategorii osoby oceniającej, do której należy dostawca lub klient:

    - Firma
    - HUF
    - Akceptuj
    - Osoba fizyczna
    - AOP
    - BOI
    - Urząd lokalny
    - Inne

    [![Skrócona karta informacji podatkowych.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. Następnie w okienku akcji, na karcie **Dostawca**, w grupie **Rejestracja** wybierz **Identyfikatory rejestracji**, aby otworzyć stronę **Zarządzaj adresami**.
10. Na stronie **Zarządzanie adresami**, na skróconej karcie **Informacje o podatku** wybierz pozycję **Dodaj** lub **Edytuj**, aby otworzyć stronę **Zarządzaj informacjami o podatku**, na której możesz zachować wpis rejestracji podatkowej.
11. Na stronie **Zarządzanie informacjami o podatkach**, na skróconej karcie **Potrącona zaliczka na podatek** w polu **Numer konta podatkowego (TAN)** wprowadź numer TAN . Znak TAN musi składać się z czterech znaków alfabetycznych, pięciu cyfr i jednego znaku alfabetycznego. Oto przykład: **AFGH54821T**.
12. Zamknij stronę.
