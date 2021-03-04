---
title: Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel
description: Ten temat zawiera informacje o sposobie modyfikowania formatu Raportowanie elektroniczne (ER) używanego do generowania dokumentów biznesowych przez ponowne zastosowanie szablonu programu Excel.
author: NickSelin
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: fa15ae3111f7b91fd63afedb3ef21709d7d866d8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682224"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modyfikowanie formatów raportowania elektronicznego przez ponowne zastosowanie szablonów programu Excel

[!include [banner](../includes/banner.md)]

Narzędzie Raportowanie elektroniczne (ER) służy do generowania dokumentów biznesowych w formacie elektronicznym. Aby wygenerować dokument biznesowy, należy utworzyć format ER, a następnie użyć projektanta ER w celu zdefiniowania układu dokumentu biznesowego i określenia danych, które powinien zawierać. Następnie można uruchomić format ER w celu wygenerowania dokumentu biznesowego.

Narzędzie ER może służyć do generowania dokumentów biznesowych w postaci plików programu Microsoft Excel. Dokumentu programu Excel można użyć jako szablonu dla tych dokumentów. Aby zdefiniować układ dokumentu w projektancie ER, można zaimportować zawartość dokumentu programu Excel, który ma zostać użyty jako szablon do zdefiniowanego formatu ER. Aby uzyskać szczegółowe informacje i przećwiczyć ten scenariusz obejrzyj przewodnik po zadaniu **ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML** (część procesu biznesowego 7.5.4.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10677)).

W przypadku edycji dokumentu programu Excel używanego jako szablon dokumentu biznesowego, nowa funkcja ER umożliwia ponowne zastosowanie zaktualizowanego szablonu do formatu ER. Format ER jest następnie aktualizowany, aby był zgodny ze zaktualizowanym szablonem. Aby uzyskać szczegółowe informacje o tej funkcji, odtwórz przewodnik po zadaniu **ER Modyfikowanie formatu przez ponowne zastosowanie szablonu programu Excel** (część procesu biznesowego 7.5.5.3 Nabywanie/opracowywanie składników usług/rozwiązań informatycznych (10683)). W kroku przewodnika po zadaniu, w którym importujesz zaktualizowany szablon, użyj zmodyfikowanego szablonu pliku programu Excel Raport o płatnościach: SampleVendPaymWsReport2, jako szablonu.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]