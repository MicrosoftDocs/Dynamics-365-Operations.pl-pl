---
title: Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel
description: Ten temat opisuje sposób modyfikowania formatu Raportowanie elektroniczne (ER) używanego do generowania dokumentów biznesowych przez ponowne zastosowanie szablonu programu Excel.
author: NickSelin
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 626450b05789c93f63675a55e050649c862c86f6
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811400"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel

[!include [banner](../includes/banner.md)]

Narzędzie Raportowanie elektroniczne (ER) służy do generowania dokumentów biznesowych w formacie elektronicznym. Aby wygenerować dokument biznesowy, należy utworzyć format ER, a następnie użyć projektanta ER w celu zdefiniowania układu dokumentu biznesowego i określenia danych, które powinien zawierać. Następnie można uruchomić format ER w celu wygenerowania dokumentu biznesowego.

Narzędzie ER może służyć do generowania dokumentów biznesowych w postaci plików programu Microsoft Excel. Dokumentu programu Excel można użyć jako szablonu dla tych dokumentów. Aby zdefiniować układ dokumentu w projektancie ER, można zaimportować zawartość dokumentu programu Excel, który ma zostać użyty jako szablon do zdefiniowanego formatu ER. Aby uzyskać szczegółowe informacje i przećwiczyć ten scenariusz obejrzyj przewodnik po zadaniu **ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML** (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)). W kroku przewodnika po zadaniach, w którym importujesz szablon programu Excel, użyj początkowego szablonu pliku Excel z raportem płatności, [SampleVendPaymWsReport](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx).

W przypadku edycji dokumentu programu Excel używanego jako szablon dokumentu biznesowego, nowa funkcja ER umożliwia ponowne zastosowanie zaktualizowanego szablonu do formatu ER. Format ER jest następnie aktualizowany, aby był zgodny ze zaktualizowanym szablonem. Aby uzyskać szczegółowe informacje o tej funkcji, odtwórz przewodnik po zadaniu **ER Modyfikowanie formatu przez ponowne zastosowanie szablonu programu Excel** (część procesu biznesowego 7.5.5.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10683)). W kroku przewodnika po zadaniu, w którym importujesz zaktualizowany szablon, użyj zmodyfikowanego szablonu pliku programu Excel Raport o płatnościach: [SampleVendPaymWsReport2](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx), jako szablonu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Aktualizowanie szablonu](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
