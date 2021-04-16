---
title: Typ miejsca docelowego drukarka
description: Ten temat zawiera wyjaśnienia dotyczące możliwości skonfigurowania miejsca docelowego drukarki dla każdego składnika typu FOLDER lub PLIK w formacie raportowania elektronicznego (ER).
author: NickSelin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 83081f8c17a903cd447a34596df2e61ebda0cafc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753439"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Miejsce docelowe — drukarka

[!include [banner](../includes/banner.md)]

Wygenerowany dokument można wysłać bezpośrednio do drukarki sieciowej w celu bezpośredniego drukowania.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować agenta rozsyłania dokumentów, a następnie zarejestrować drukarki sieciowe. W celu zdobycia większezj ilości informacji, zobacz [Instalowanie Agenta rozsyłania dokumentów w celu obsługi druku przez sieć](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).

## <a name="make-the-printer-destination-available"></a>Umożliwia udostępnienie drukarki jako miejsca docelowego

Aby udostępnić **drukarkę** jako miejsce docelowe w bieżącej instancji rozwiązania Microsoft Dynamics 365 Finance, przejdź do obszaru roboczego **zarządzanie funkcją** i włącz funkcje w następującej kolejności:

1. Konwertuj dokumenty wychodzące raportowania elektronicznego z formatów Microsoft Office na PDF
2. Agent rozsyłania dokumentów jako cel raportowania elektronicznego dla dokumentów wychodzących

[![Włączanie funkcji lokalizacji docelowej drukarka ER w module Zarządzanie funkcjami](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Możliwość zastosowania

Lokalizację docelową **Drukarka** można skonfigurować tylko dla składników plików używanych do generowania danych wyjściowych w formacie PDF (format PDF lub w formacie PDF) lub Microsoft Office Excel / formacie Word (plik programu Excel). Jeśli dane wyjściowe są generowane w formacie PDF, są one wysyłane do drukarki. Jeśli dane wyjściowe są generowane w formacie Microsoft Office, są automatycznie konwertowane na format PDF, a następnie wysyłane na drukarkę.

### <a name="limitations"></a>Ograniczenia

Lokalizacja docelowa **Drukarka** jest zaimplementowana tylko dla wdrożeń w chmurze.

### <a name="use-the-printer-destination"></a>Użyj miejsca docelowego drukarka

1. Ustawienie opcji **włączone** na wartość **Tak** powoduje wysłanie wygenerowanego dokumentu do drukarki.
2. W polu **Nazwa drukarki** wybierz żądaną drukarkę sieciową.
3. Ustawienie parametrt **Zapisywanie w archiwum drukowania?** na wartość **Tak** spowoduje przechowywanie wygenerowanych danych wyjściowych w archiwum drukowania, tak aby było dostępne do dalszego drukowania. Aby później uzyskać dostęp do zarchiwizowanych danych wyjściowych **Zarządzanie organizacją** \> **Raporty i zapytania** \> **Archiwum raportów**.

[![Używanie miejsca docelowego drukarka](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> Opcja **Konwertuj na plik PDF** nie musi być włączona podczas konfigurowania miejsca docelowego **Drukarka**. Konwersja plików PDF na potrzeby drukowania nastąpi nawet wtedy, gdy opcja jest wyłączona.

Aby podczas drukowania dokumentu wychodzącego w formacie programu Excel używana była określona [orientacja strony](electronic-reporting-destinations.md#SelectPdfPageOrientation), należy włączyć opcję **Konwertuj na PDF**. Ustawienie opcji **Konwertuj na PDF** na wartość **Tak** powoduje, że staje się dostępne pole **Orientacja strony**. W polu **Orientacja strony** możesz wybrać orientację strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
