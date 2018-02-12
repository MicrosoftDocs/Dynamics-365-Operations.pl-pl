---
title: "Przepływ pracy dotyczący wydatków"
description: "W tym temacie wyjaśniono, jak korzystać z systemu przepływu pracy w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, w celu skonfigurowania procesu kontroli dla raportu wydatków w funkcji Zarządzanie wydatkami."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d60d2f462a1fd27d4655e68aab7f96fb28a34b77
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="expense-workflow"></a>Przepływ pracy dotyczący wydatków

[!include[banner](../includes/banner.md)]

Systemu przepływu pracy w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, można użyć w celu skonfigurowania procesu kontroli dla raportu wydatków w funkcji Zarządzanie wydatkami. Można skonfigurować przepływ pracy, który używa następujących kryteriów do określenia osoby zatwierdzającej raporty wydatków:

- Hierarchia raportowania pracownika i wstępnie zdefiniowane limity zatwierdzenia
- Wielopoziomowe zatwierdzanie, które obsługuje osoby zatwierdzające tymczasowo i osobę ostatecznie zatwierdzającą
- Wymiary finansowe i odpowiedzialność za projekt
- Przypisanie do określonych użytkowników lub grup użytkowników

Zatwierdzenia przepływu pracy można utworzyć dla raportów z wydatków, wniosków wyjazdowych, zaliczek gotówkowych i zwrotu podatku VAT.

**Przykład**

Poniżej przedstawiono przykładowy przepływ pracy zarządzania wydatkami w odniesieniu do raportu z wydatków.

1. Pracownik tworzy i zapisuje raport z wydatków.
2. Pracownik przesyła raport z wydatku do zatwierdzenia. Osoba zatwierdzająca jest identyfikowana na podstawie zasad zdefiniowanych podczas konfigurowania przepływu pracy.
3. Osoba zatwierdzająca otrzymuje powiadomienie, że raport z wydatków jest gotowy do zatwierdzenia. Osoba zatwierdzająca sprawdza raport z wydatków i weryfikuje spełnienie następujących warunków:

    - Wydatki nie są niezgodne z zasadami dotyczącymi wydatków. Jeżeli wydatek narusza zasady, osoba zatwierdzająca sprawdza, czy raport z wydatków zawiera prawidłowe uzasadnienie biznesowe.
    - Do raportu z wydatków są dołączone pokwitowania elektroniczne.

4. Osoba zatwierdzająca zatwierdza raport z wydatków.
5. Raport z wydatków zostaje przypisany do osoby odpowiedzialnej za rozrachunki z dostawcami w celu zaksięgowania.
6. W zależności od tego, czy skonfigurowano automatyczne księgowanie, wykonywany jest jeden z następujących kroków:

    - Jeżeli skonfigurowano automatyczne księgowanie, raport z wydatków jest przetwarzany w celu płatności, a stan raportu z wydatków jest aktualizowany.
    - Jeżeli automatyczne księgowanie nie jest skonfigurowane, osoba odpowiedzialna za rozrachunki z dostawcami sprawdza, czy wszystkie oryginalne pokwitowania zostały przesłane i są zgodne z wydatkami w raporcie. Wszystkie kody podatków wprowadzone w raporcie z wydatków także muszą zostać zweryfikowane jako prawidłowe.

Po zweryfikowaniu tych wymagań raport z wydatków jest księgowany.

Po zaksięgowaniu raportu z wydatków płatność jest autoryzowana dla raportu z wydatków, a pracownik otrzymuje zwrot.

