---
title: Dane zewnętrzne w prognozach przepływów pieniężnych
description: W tym artykule opisano czynności konfiguracyjne, które należy wykonać, aby można było wprowadzać i importować dane zewnętrzne do prognoz przepływów pieniężnych.
author: RyanCCarlson2
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f0cb05770dc2fbd4e13af261b5f0a0e117a2f6d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846981"
---
# <a name="external-data-in-cash-flow-forecasts"></a>Dane zewnętrzne w prognozach przepływów pieniężnych

[!include [banner](../includes/banner.md)]

Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych. W tym artykule opisano czynności konfiguracyjne właściwe dla korzystania z danych zewnętrznych, które umożliwiają uwzględnienie danych zewnętrznych w prognozie przepływów pieniężnych.

## <a name="external-data-setup"></a>Ustawienia danych zewnętrznych

Karta **Źródło zewnętrzne** na stronie **Ustawienia prognozy przepływów pieniężnych** (**Zarządzanie gotówką i bankami \> Prognozowanie przepływów pieniężnych \> Ustawienia prognozy przepływów pieniężnych**) służy do wprowadzania ustawień, które pozwalają na używanie danych zewnętrznych w prognozach przepływów pieniężnych.

Dane zewnętrzne można wprowadzać lub importować do prognoz przepływów pieniężnych. Przed wprowadzeniu lub zaimportowaniu danych zewnętrznych należy skonfigurować źródła zewnętrzne. Na karcie **Źródło zewnętrzne** skonfiguruj kategorie zewnętrznych przepływów pieniężnych. Może to być kategoria **Wychodząca** lub **Przychodząca**. Jako typ księgowania należy wybrać **płynność**. W siatce **Ustawienia firmy wybierz firmy** i odpowiednie konta główne, do których mają zastosowanie kategorie zewnętrznych przepływów pieniężnych.

Więcej informacji na temat uruchamiania Prognozy przepływów pieniężnych znajdziesz: [Prognozy przepływów pieniężnych](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Wprowadź dane zewnętrzne

Aby wprowadzać i modyfikować dane zewnętrzne na potrzeby prognoz przepływów pieniężnych, możesz użyć środowiska **Otwórz w programie Excel**. Wybierz przycisk **Dane zewnętrzne** na stronie obszaru roboczego **Prognoza przepływów pieniężnych**, a następnie wybierz opcję **Dodaj dane zewnętrzne** lub **Edytuj istniejące dane zewnętrzne**. Po otwarciu pliku programu Microsoft Excel można wprowadzić informacje w następujących polach:

- **Identyfikator wpisu** (unikatowy)
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
