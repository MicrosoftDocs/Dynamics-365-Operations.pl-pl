---
title: Importowanie konfiguracji polecenia przelewu ISO20022
description: W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ffc86ba9dade0ae494ca4ace8d9f562da9c9527a4731493d892b60112293af3f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781143"
---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importowanie konfiguracji polecenia przelewu ISO20022

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy. Jako przykładu użyto niemieckiego formatu poleceń przelewu zgodnego z normą ISO 20022. Procedura może być używana do innych dostępnych formatów raportowania elektronicznego. 

Zadanie zostało utworzone przy użyciu danych firmy demonstracyjnej DEMF, ale do wykonania zadania można użyć danych dowolnej firmy demonstracyjnej.

Jest to pierwsze z pięciu zadań, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Na liście dostępnych dostawców konfiguracji zaznacz pozycję Microsoft.
3. Kliknij opcję Ustaw jako aktywny.
4. Kliknij Repozytoria.
5. Kliknij przycisk Otwórz.
6. Kliknij przycisk Pokaż filtry.
7. Zastosuj następujące filtry: w polu „Nazwa konfiguracji” wprowadź wartość filtru „Polecenie przelewu ISO20022 (Niemcy)”, używając operatora filtru „zaczyna się od”.
    * Alternatywnie można poszukać konfiguracji na liście, zaznaczyć ją, a następnie przenieść do zadania importu.  
8. Kliknij przycisk Importuj.
    * Jeśli przycisk Importuj nie jest dostępny, oznacza to, że konfiguracja została już zaimportowana.  
9. Kliknij przycisk Tak.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]