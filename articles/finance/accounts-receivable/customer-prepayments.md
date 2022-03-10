---
title: Przedpłaty klienta
description: W tym temacie wyjaśniono, jak tworzyć i przetwarzać przedpłaty odbiorcy (zwane także wpłatami klientów).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e83c8be1b397f90445230835e415ea4fcea5a8d0bf695e6cc5eadc55275ded7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768970"
---
# <a name="customer-prepayments"></a>Przedpłaty klienta

[!include [banner](../includes/banner.md)]

Przedpłaty odbiorcy są używane, gdy użytkownik otrzymuje płatność od odbiorcy, ale nie ma faktury, z która można rozliczyć płatność. Te typy płatności są nazywane również wpłatami klientów.

Proces konfigurowania przedpłat odbiorcy i pracy z nim składa się z następujących podstawowych kroków.

1. Tworzenie profilu księgowania odbiorcy dla przedpłat.
2. Ustaw parametr **Profil księgowania z użyciem załącznika arkusza zaliczki**.
3. Utwórz arkusz płatności odbiorcy i zaznacz pole wyboru **Załącznik arkusza przedpłat** w każdym wierszu.
4. Księgowanie arkusza płatności odbiorcy.
5. Po wygenerowaniu faktury rozlicz przedpłatę przy użyciu strony **Rozlicz otwarte transakcje**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Tworzenie profilu księgowania odbiorcy dla przedpłat

Zazwyczaj w przypadku akceptowania przedpłat lub depozytów od odbiorców przed dostarczonem towarem lub usługą lub przed dodaniem faktury w systemie użytkownik chce zarejestrować gotówkę jako pasywa, a nie środek w plan kont. Jednak wymagania dotyczące rejestrowania tych kwot w księdze głównej mogą się różnić w zależności od kraju lub regionu. Dlatego należy skonsultować się z księgowymi w sprawie wszystkich obowiązujących lokalnych przepisów.

Na ogół proces tworzenia profilu księgowania, który może być używany dla przedpłat, jest taki sam jak proces tworzenia innych profilów księgowania. Główną różnicą jest konto główne wybrane w polu **Konto podsumowujące**. Aby uzyskać więcej informacji, zobacz [Profile księgowania odbiorców](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Definiuj parametry przedpłat odbiorcy

Istnieją dwa główne parametry rozrachunków z odbiorcami, które należy uwzględnić podczas konfigurowania systemu dla przedpłat odbiorcy. Wykonaj poniższe czynności, aby skonfigurować parametry.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
2. Opcjonalnie: na karcie **Księga i podatek** na skróconej karcie **Płatność** ustaw dla opcji **Załącznik arkusza zaliczki** wartość **Tak**.
3. W polu **Profil księgowania załącznik arkusza zaliczki** wybierz profil księgowania odbiorcy do zastosowania podczas księgowania przedpłat odbiorcy.
4. Zamknij stronę.

## <a name="create-customer-prepayment-vouchers"></a>Tworzenie załączników przedpłat odbiorcy

Podczas tworzenia arkusza płatności odbiorcy dla każdej przedpłaty trzeba ustawić opcję **Załącznik arkusza przedpłat** **Tak** na stronie **Arkusz płatności odbiorcy**. Wykonaj poniższe czynności, aby utworzyć przedpłatę klienta.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Płatności \> Arkusz płatności klienta**.
2. Wybierz **Nowa**, aby utworzyć arkusz.
3. W polu **Nazwa** wybierz nazwę arkusza, która ma być używana.

    > [!IMPORTANT]
    > W przypadku ustawienia dla opcji **Podatek załącznik arkusza zaliczki** opcji **Tak** w poprzedniej procedurze należy wybrać nazwę arkusza, w której zaznaczono parametr **Kwota zawiera podatek**. 

4. Opcjonalnie: W polu **opis** wprowadź szczegółowy opis.
5. Wybierz **Linie**.
6. Jeśli pusty wiersz nie istnieje, wybierz przycisk **Nowy**, aby utworzyć wiersz.
7. W polu **Data** należy wpisać datę zaksięgowania przedpłaty.
8. W polu **Konto** wybierz odbiorcę przedpłaty.
9. Opcjonalnie: W polu **opis** wprowadź szczegółowy opis transakcji.
10. W polu **Kredyt** wprowadź kwotę przedpłaty.
11. W polu **Typ konta przeciwstawnego** wybierz konto, na które chcesz przeliczyć płatność. Na przykład wybierz konto bankowe lub główne, w których ma być zaksięgowana płatność.
12. W polu **Metody płatności** wybierz sposób płatności klienta.
13. Na karcie **Płatność** ustaw opcję **Załącznik arkusza przedpłat** o wartości **Tak**.
14. Powtórz kroki od 7 do 13 dla każdej dodatkowej zaliczki, która musi zostać zaksięgowana.
15. Wybierz **Publikowanie**, aby sfinalizować dziennik.

## <a name="settle-prepayments-with-invoices"></a>Rozlicz przedpłaty za pomocą faktur

Obszar roboczy **Płatności odbiorcy** umożliwia łatwe znajdowanie i rozliczanie płatności, które nie zostały w pełni rozliczone.

1. Na **głównym** pulpicie nawigacyjnym wybierz kafelek **płatności odbiorcy**.
2. W sekcji **Transakcje odbiorcy** na karcie **Płatności nie rozliczone** wyszukaj i wybierz płatność do rozliczenia.
3. Wybierz **Rozlicz transakcje**.
4. Zaznacz pole wyboru **Zaznacz** dla faktury i płatność, która zostanie rozliczona.
5. Wybierz opcję **Zaksięguj**.

Aby uzyskać więcej informacji o rozliczaniu otwartych transakcji, zobacz [Przegląd rozliczania](/cash-bank-management/settlement-overview.md).
