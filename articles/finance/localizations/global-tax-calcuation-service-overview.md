---
title: Obliczanie podatku (wersja zapoznawcza)
description: W tym temacie wyjaśniono ogólny zakres i funkcje obliczania podatku.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bab6e0e0ea1b9fb7f598e37843b52e3ba9c7f94e
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336639"
---
# <a name="tax-calculation-preview"></a>Obliczanie podatku (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Obliczanie podatku to hyper-skalowalna usługa wielowątkowa, która umożliwia aparatowi Global tax engine automatyzowanie i upraszczanie procesu określania i obliczania podatków. Aparat podatków jest w pełni konfigurowalny. Elementy, które można konfigurować, obejmują model danych podlegających opodatkowaniu, kod podatku, macierz możliwości stosowania podatku oraz formułę obliczania podatku. Aparat podatków działa na podstawowej platformie usług Microsoft Azure i oferuje nowoczesne technologie oraz skalowalność.

Obliczanie podatku jest zintegrowane z Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Można ją także zintegrować Dynamics 365 Project Operations i Dynamics 365 Commerce z innymi aplikacjami firmy i innych firm.

> [!IMPORTANT]
> Po włączeniu usługi Obliczanie podatku niektóre operacje na powiązanych danych mogą być wykonywane w centrum danych innym niż centrum danych, w którym przechowywane są dane usługi. Zapoznaj się z [Regulaminem korzystania](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) przed włączeniem usługi Obliczanie podatku. Prywatność użytkowników jest dla nas bardzo ważna. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).

Obliczanie podatku jest mikrousługą opartą na firmie Microsoft aparatem podatków, która oferuje wystawczą skalowalność. Możne pomóc wykonać następujące zadania:

- Skonfiguruj usługę Obliczania podatku za pomocą Regulatory Configuration Service (RCS). Usługa RCS jest rozszerzoną wersją konstruktora raportowania elektronicznego i jest dostępna jako autonomiczna usługa.
- Umożliwia konfigurowanie macierzy podatków w celu automatycznego określania kodów i stawek podatkowych.
- Skonfiguruj macierz podatkową, aby automatycznie określić numer rejestracji podatkowej.
- Skonfiguruj projektanta obliczeń podatku w celu zdefiniowania formuł i warunków.
- Udostępnij rozwiązanie dotyczące określania podatków i obliczania w różnych firmach.

Aby użyć usługi obliczania podatku, zainstaluj dodatek usługi obliczania podatku z swojego projektu w usłudze Microsoft Dynamics Lifecycle Services (LCS). Następnie należy ukończyć konfigurację w rcs i włączyć usługę obliczania podatku w Finance i Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Rozpocznij pracę z usługą podatkową](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Dostępność

Obliczanie podatku jest dostępne tylko w środowiskach piaskownicy i dla wybranych klientów za pośrednictwem publicznego programu w wersji zapoznawczej. Ostatecznie stają się one ogólnie dostępne dla wszystkich odbiorców oraz w środowiskach produkcyjnych.

Nowe funkcje będą nadal dostarczane, więc pamiętaj, aby często sprawdzać najbardziej aktualną dokumentację, aby dowiedzieć się o zasięgu i zakresie obsługiwanych funkcji.

Obliczanie podatku jest wdrożone w następujących lokalizacjach geograficznych systemu Azure. Zostanie on również wdrożony w większej liczby geografów systemu Azure w zależności od potrzeb klientów:

- Stany Zjednoczone
- Europa

> [!NOTE]
> Obliczanie podatku nie obsługuje lokalnych wdrożeń rozwiązania Dynamics 365. Nie obsługuje także wcześniejszych wersji, takich jak Dynamics AX 2012.

## <a name="feature-highlights"></a>Najważniejsze cechy

- Konfigurowalna macierz podatkowa do automatycznego określania i obliczania podatku
- Obsługa wielu numerów rejestracji podatkowej
- Obsługa zamówień przeniesienia do określania i obliczania podatku
- Obsługa zamówień przeniesienia w celu określenia wielu numerów rejestracji podatkowej

## <a name="supported-transactions"></a>Obsługiwane transakcje

Obliczanie podatku może być włączone przez firmę i transakcję. Obsługiwane są następujące transakcje:

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

[Rozpocznij pracę z usługą podatkową](./global-get-started-with-tax-calculation-service.md)

[Wielokrotny numer rejestracji VAT](./emea-multiple-vat-registration-numbers.md)

[Obsługa funkcji podatków dla zamówienia przeniesienia](./tasks/tax-feature-support-for-transfer-order.md)

[Jak utworzyć rozszerzenie w usłudze podatków](./tax-service-add-data-fields-tax-integration-by-extension.md)
