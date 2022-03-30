---
title: Zapisz możliwe do odzyskania numery certyfikatów TDS
description: W tym temacie wyjaśniono, jak używać strony Certyfikaty podlegające zwrotowi do rejestracji numerów certyfikatów i dat dla certyfikatów potrącanych z podatku w źródle (TDS), które są odbierane dla określonego dostawcy, odbiorcy lub księgi.
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
ms.openlocfilehash: 8fa4d1200818b4657b044a376ebb292426250ae1
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407747"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Zapisz możliwe do odzyskania numery certyfikatów TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak używać strony **Certyfikaty podlegające zwrotowi** do rejestracji numerów certyfikatów i dat dla certyfikatów potrącanych z podatku w źródle (TDS), które są odbierane dla określonego dostawcy, odbiorcy lub księgi. Aby zaktualizować numery i daty certyfikatów TDS zarejestrowane dla transakcji TDS na tej stronie, użyj strony **Aktualizuj certyfikat** (**Księga główna \> Okres \> Potrącona zaliczka na podatek \> Aktualizuj certyfikaty**). Po zakończeniu aktualizowania numerów certyfikatów TDS należy je zamknąć.

Aby zarejestrować numery i daty certyfikatów TDS, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Certyfikaty podlegające zwrotowi**.

    [![Strona certyfikatów zwrotnych.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. Na stronie **Certyfikaty objętych zwrotem** w polu **Typ podatku** wybierz pozycję **TDS**.
3. Wybierz **Nowy**, aby utworzyć rekord.
4. W polu **Numer certyfikacji** wprowadź numer certyfikatu koncesji TDS.
5. W polu **Typ konta** wybierz typ konta, dla których otrzymano certyfikat TDS: **Dostawca**, **Odbiorca** lub **Księga**.
6. W polu **Konto** wybierz dostawcę, konto odbiorcy lub numer konta księgowego, w zależności od wybranego typu konta. Pole **Nazwa** zawiera nazwę dostawcy, odbiorcy lub konta księgowego.
7. W polu **Kwota certyfikacji** wprowadź kwotę certyfikatu TDS.
8. W polu **Data** wprowadź datę dla numeru certyfikatu.
9. Wybierz opcję **Informacje**, aby otworzyć stronę **Transakcje certyfikatu**, na której możesz przejrzeć transakcje TDS, dla których zaktualizowano numer i datę certyfikatu TDS. Te informacje można zaktualizować na stronie **Aktualizuj certyfikat** (**Podatek \> Deklaracje \> Potrącona zaliczka na podatek \> Aktualizuj certyfikaty**).

    Na stronie **Aktualizuj certyfikaty** są podane następujące informacje dotyczące każdej otwartej transakcji TDS:

    - **Data** – Data księgowania transakcji TDS.
    - **Załącznik** – Umożliwia wyświetlenie numeru załącznika TDS.
    - **Źródło** — moduł, w których jest utworzona transakcja TDS.
    - **Konto** — numer dostawcy, odbiorcy lub konta księgowego, dla których została utworzona transakcja TDS.
    - **Nazwa** — Nazwa dostawcy, odbiorcy lub konta księgowego, dla którego utworzono transakcję TDS.
    - **Kwota** – Kwota faktury, na podstawie której obliczono TDS.
    - **Kwota podatku** — kwota podatku TDS obliczona dla transakcji.
    - **Data certyfikatu** — data certyfikatu TDS zaktualizowana dla transakcji TDS.
    - **Numer certyfikatu** — numer certyfikatu TDS zaktualizowana dla transakcji TDS.

10. Na stronie **Certyfikaty możliwe do zwrotu** zaznacz pole wyboru **Zamknięte**, aby zamknąć numer certyfikatu TDS po zakończeniu aktualizowania go dla transakcji TDS na stronie **Aktualizacja certyfikatu**.

    Aby zaznaczyć pole wyboru **Zamknięte** dla wszystkich rekordów na stronie, zaznacz opcję **Zaznacz wszystko**.

    > [!NOTE]
    > Numery certyfikatów TDS, dla których zaznaczono pole wyboru **Zamknięte**, nie są dostępne na stronie **Aktualizacja certyfikatu**.
