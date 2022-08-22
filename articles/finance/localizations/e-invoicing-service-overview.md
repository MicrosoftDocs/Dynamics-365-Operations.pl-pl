---
title: Omówienie fakturowania elektronicznego
description: Ten artykuł zawiera omówienie fakturowania elektronicznego w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 01/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 7602234f875735537f0cabff135b0e0b650e5b96
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269477"
---
# <a name="electronic-invoicing-overview"></a>Omówienie fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Faktury elektroniczne dla Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management to hiper-skalowalna usługa dla wielu dzierżawców, która umożliwia konfigurowalne przetwarzanie faktur elektronicznych i konfigurowalną elektroniczną wymianę dokumentów. Reguły przetwarzania i integracji są w pełni konfigurowalne, a logika działa poza rozwiązaniami Finance and Supply Chain Management. Usługa jest docelowa głównie na potrzeby przetwarzania dokumentów faktur elektronicznych w scenariuszach od firmy do instytucji rządowych. Można go jednak konfigurować niestandardowo dla innych celów, takich jak scenariusze między firmami dla różnych typów dokumentów.

Faktury elektroniczne może pomóc w osiągnięciu następujących celów:

- Szybkie i łatwe przyjęcie wymagań specyficznych dla kraju/regionu
- Standaryzowane implementacje rozwiązania Faktur elektronicznych
- Ulepszona możliwość śledzenia historii dokumentów
- Krótszy cykl implementacji
- Obniżony całkowity koszt użytkowania (TCO)
- Łatwe do regulowania konfiguracje, które nie wymagają zmiany kodu
- Uproszczone pakowanie konfiguracji
- Wbudowana funkcja eksportowania, importowania i integrowania oraz łatwa rozszerzalność w przetwarzaniu dokumentów faktur elektronicznych
- Łatwe ponowne wykorzystanie tych samych konfiguracji eksportu, importu i integracji w różnych firmach

## <a name="service-availability"></a>Dostępność usługi

Obecnie funkcje fakturowania elektronicznego są dostępne dla odbiorców w ramach zarządzania finansami i Supply Chain Management. Aby uzyskać więcej informacji, należy zapoznać się z postanowieniami licencyjnmi aplikacji.

Ponieważ funkcjonalność, która spełnia wymagania specyficzne dla kraju/regionu, może być ograniczona na różnych etapach wydania, należy zawsze sprawdzać najbardziej aktualną dokumentację, która podkreśla zakres i zakres obsługiwanych rozwiązań specyficznych dla kraju/regionu.

Faktury elektroniczne są wdrażane w następujących lokalizacjach geograficznych platformy Azure:

- Stany Zjednoczone
- Europa
- Azja

> [!NOTE]
> Faktury elektroniczne nie obsługuje wdrożeń lokalnych.

## <a name="feature-highlights"></a>Najważniejsze cechy

- Bezpośrednia integracja z Finance i Supply Chain Management
- Spójny interfejs użytkownika do konfiguracji i monitorowania procesu faktur elektronicznych dla wszystkich krajów i regionów
- Szybsze, łatwiejsze i tańsze wdrażanie rozwiązań faktur elektronicznych w nowych krajach lub regionach
- Konfiguracja usługi poprzez konfigurację Regulatory Configuration Service (RCS) i funkcji Globalization
- Przekształcenie danych biznesowych w wiele formatów faktur elektronicznych (XML, JavaScript Object Notation \[JSON\], TXT i wartości rozdzielane przecinkami \[CSV\]) przy użyciu konfiguracji zdefiniowanych w RCS:

    - Formaty raportowania elektronicznego (ER), które są dostępne dla krajów lub regionów, w których nie jest dostępna konfigurowalność przekształcania faktur elektronicznych

- Konfigurowalne przesyłanie faktur elektronicznych do zewnętrznych usług internetowych, w tym obsługa certyfikacji za pomocą podpisów cyfrowych:

    - Wbudowana, łatwo rozszerzalna i konfigurowalna integracja z dodatkowymi treściami dla kilku krajów i regionów

- Obsługa odpowiedzi z usług internetowych, w tym konfigurowalna obsługa komunikatów o wyjątkach
- Obsługa podpisów elektronicznych (na przykład podpisów elektronicznych wykorzystujących algorytm podpisywania XMLDSig)
- Możliwość wysyłania dokumentów do wiadomości e-mail i przechowywania ich w SharePoint
- Przetwarzanie wsadowe wiadomości faktur elektronicznych
- Konfigurowalne przekształcenie dokumentów przychodzących oraz przetwarzanie tych dokumentów w zarządzaniu finansami i Supply Chain Management
- Możliwość otrzymywania dokumentów przychodzących z kanałów takich jak poczta e-mail i SharePoint

## <a name="privacy-notice"></a>Klauzula prywatności

Włączenie i korzystanie z fakturowania elektronicznego może wymagać przesyłania ograniczonych danych. Te dane obejmują identyfikator podatkowy organizacji. Dane te będą przekazywane agencjom zewnętrznym upoważnionym przez organy podatkowe w celu wysyłania faktur elektronicznych we wstępnie zdefiniowanych formatach wymaganych do integracji z rządowymi usługami internetowymi. Dane importowane z tych systemów zewnętrznych do tej usługi online, która wchodzi w skład usługi Dynamics 365, podlegają naszemu [oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=512132). Aby uzyskać więcej informacji, zapoznaj się z sekcją „Uwagi dotyczące prywatności” w dokumentacji funkcji specyficznej dla kraju/regionu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
