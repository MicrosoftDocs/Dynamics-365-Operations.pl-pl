---
title: Usługa obliczania podatku (wersja zapoznawcza)
description: W tym temacie wyjaśniono ogólny zakres i funkcje usługi obliczania podatku.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818231"
---
# <a name="tax-calculation-service-preview"></a>Usługa obliczania podatku (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Usługa obliczania podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków. Aparat podatków jest w pełni konfigurowalny. Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku. Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.

Usługa obliczania podatku jest zintegrowana z Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.

Usługa obliczania podatku jest opartym na firmie Microsoft aparatem podatków, który oferuje wystawczą skalowalność. Możne pomóc wykonać następujące zadania:

- Skonfiguruj usługę obliczania podatku za pomocą usługi konfiguracji przepisów (RCS). Usługa RCS jest rozszerzoną wersją konstruktora raportowania elektronicznego i jest dostępna jako autonomiczna usługa.
- Umożliwia konfigurowanie macierzy podatków w celu automatycznego określania kodów i stawek podatkowych.
- Skonfiguruj macierz podatkową, aby automatycznie określić numer rejestracji podatkowej.
- Skonfiguruj projektanta obliczeń podatku w celu zdefiniowania formuł i warunków.
- Udostępnij rozwiązanie dotyczące określania podatków i obliczania w różnych firmach.

Aby użyć usługi obliczania podatku, zainstaluj dodatek usługi obliczania podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services (LCS). Następnie należy ukończyć konfigurację w rcs i włączyć usługę obliczania podatku w Finance i Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](https://go.microsoft.com/fwlink/?linkid=2138482).

## <a name="availability"></a>Dostępność

Usługa obliczania podatku jest dostępna tylko w środowiskach piaskownicy i dla wybranych klientów za pośrednictwem publicznego programu w wersji Preview. Ostatecznie stają się one ogólnie dostępne dla wszystkich odbiorców oraz w środowiskach produkcyjnych.

W usłudze obliczania podatku będą dostarczane nowe funkcje. Dlatego należy często sprawdzać najczęściej dostępną dokumentację, aby dowiedzieć się o zakresie i zakresie obsługiwanych funkcji.

Usługa obliczania podatku jest wdrożona w następujących lokalizacjach geograficznych systemu Azure. Zostanie on również wdrożony w większej liczby geografów systemu Azure w zależności od potrzeb klientów:

- Stany Zjednoczone
- Europa
- Francja
- Wielka Brytania

> [!NOTE]
> Usługa obliczania podatku nie obsługuje lokalnych wdrożeń rozwiązania Dynamics 365. Nie obsługuje także wcześniejszych wersji, takich jak Dynamics AX 2012.

## <a name="feature-highlights"></a>Najważniejsze cechy

- Konfigurowalna macierz podatkowa do automatycznego określania i obliczania podatku
- Obsługa wielu numerów rejestracji VAT
- Obsługa zamówień przeniesienia do określania i obliczania podatku
- Obsługa zamówień przeniesienia w celu określenia wielu numerów rejestracji VAT

## <a name="supported-transactions"></a>Obsługiwane transakcje

Usługa obliczania podatku może być włączona przez firmę i transakcję. Obsługiwane są następujące transakcje:

- Proces sprzedaży

    - Oferta sprzedaży
    - Zamówienie sprzedaży
    - Potwierdzenie
    - Lista pobrania
    - Dokument dostawy
    - Faktura sprzedaży
    - Faktura kredytowa
    - Zwróć zamówienie
    - Nagłówek Opłaty dodatkowe
    - Pozostały koszt dotyczący danej pozycji

- Proces zakupu

    - Zamówienie zakupu
    - Potwierdzenie
    - Lista przychodu
    - Dokument przyjęcia produktów
    - Faktura zakupu
    - Nagłówek Opłaty dodatkowe
    - Pozostały koszt dotyczący danej pozycji
    - Faktura kredytowa
    - Zwróć zamówienie
    - Zapotrzebowanie na zakup
    - Różne obciążenia wiersza zapotrzebowania na zakup
    - Zapytanie ofertowe
    - Różne opłaty od nagłówka zapytania ofertowego
    - Różne opłaty od wiersza zapytania ofertowego

- Proces zapasów

    - Przeniesienie zamówienia - wysyłka
    - Zamówienie przeniesienia - odbiór

## <a name="related-resources"></a>Powiązane zasoby

[Rozpocznij pracę z usługą podatkową](https://go.microsoft.com/fwlink/?linkid=2138482)

[Wielokrotny numer rejestracji VAT](https://go.microsoft.com/fwlink/?linkid=2153387)

[Obsługa funkcji podatków dla zamówienia przeniesienia](https://go.microsoft.com/fwlink/?linkid=2153388)

[Jak utworzyć rozszerzenie w usłudze podatków](https://go.microsoft.com/fwlink/?linkid=2138483)
