---
title: Używanie danych zewnętrznych w prognozach przepływów pieniężnych
description: W tym temacie opisano czynności konfiguracyjne, które należy wykonać, aby można było wprowadzać i importować dane zewnętrzne do prognoz przepływów pieniężnych.
author: rcarlson
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 855f428ae8ce79f2b7ce9a6f3347cd454bad9566
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386469"
---
# <a name="use-external-data-in-cash-flow-forecasts"></a>Używanie danych zewnętrznych w prognozach przepływów pieniężnych

[!include [banner](../includes/banner.md)]

Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych. W tym temacie opisano czynności konfiguracyjne właściwe dla korzystania z danych zewnętrznych, które umożliwiają uwzględnienie danych zewnętrznych w prognozie przepływów pieniężnych.

## <a name="external-data-setup"></a>Ustawienia danych zewnętrznych

Karta **Źródło zewnętrzne** na stronie **Ustawienia prognozy przepływów pieniężnych** (**Zarządzanie gotówką i bankami \> Prognozowanie przepływów pieniężnych**) służy do wprowadzania ustawień, które pozwalają na używanie danych zewnętrznych w prognozach przepływów pieniężnych.

Aby uzyskać więcej informacji o konfiguracji, zobacz temat [Prognozowanie przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).

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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
