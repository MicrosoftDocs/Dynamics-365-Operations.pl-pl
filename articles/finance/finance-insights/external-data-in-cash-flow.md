---
title: Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano czynności konfiguracyjne, które należy wykonać, aby można było wprowadzać i importować dane zewnętrzne do prognoz przepływów pieniężnych.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae0eba6d397725cf425d9781a597d904e1958d44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009400"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Używanie danych zewnętrznych w prognozach przepływów pieniężnych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych. W tym temacie opisano czynności konfiguracyjne właściwe dla korzystania z danych zewnętrznych, które umożliwiają uwzględnienie danych zewnętrznych w prognozie przepływów pieniężnych.

## <a name="external-data-setup"></a>Ustawienia danych zewnętrznych

Karta **Źródło zewnętrzne** na stronie **Ustawienia prognozy przepływów pieniężnych** (**Zarządzanie gotówką i bankami \> Prognozowanie przepływów pieniężnych**) służy do wprowadzania ustawień, które pozwalają na używanie danych zewnętrznych w prognozach przepływów pieniężnych.

Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Prognozowanie przepływów pieniężnych](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

Aby wprowadzić dane zewnętrzne dla prognoz przepływów pieniężnych, można skorzystać z funkcji Otwórz w programie Excel służącej do wprowadzania i modyfikowania danych zewnętrznych. Wybierz przycisk **Dane zewnętrzne**, a następnie wybierz opcję **Dodaj dane zewnętrzne** lub **Edytuj istniejące dane zewnętrzne**. Po otwarciu pliku programu Microsoft Excel można wprowadzić informacje w następujących polach:

- **Identyfikator wpisu**
- **Opis** (opcjonalnie)
- **Nazwa źródła zewnętrznego** — wybierz jedną z wartości z listy zdefiniowanej podczas konfigurowania modułu Finance Insights.
- **Osoba prawna**
- **Data**
- **Kwota w walucie transakcji**
- **Kod waluty**
- **Wymiar domyślny** (opcjonalnie)
- **Numer dokumentu** (opcjonalnie)
- **Numer konta** (opcjonalnie)
- **Nazwa konta** (opcjonalnie)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importowanie danych zewnętrznych przy użyciu struktury zarządzania danymi

Dane zewnętrzne dla prognoz przepływów pieniężnych można importować za pomocą obszaru roboczego **Zarządzanie danymi** i jednostki o nazwie **Wprowadzanie z zewnętrznego źródła dla prognozy przepływów pieniężnych**.

Ponadto jeśli trzeba przenieść dane konfiguracyjne z jednego środowiska do drugiego, dostępne są następujące jednostki dla wymaganych tabel konfiguracji:

- Konfiguracja zewnętrznego źródła prognozowania przepływów pieniężnych
- Konfiguracja firmy zewnętrznego źródła prognozowania przepływów pieniężnych

#### <a name="privacy-notice"></a>Klauzula prywatności
Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]