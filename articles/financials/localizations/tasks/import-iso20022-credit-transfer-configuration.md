--- 
title: Importowanie konfiguracji polecenia przelewu ISO20022
description: "W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 52d502a53deb6defa619af4ca8cdc3158e086bae
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a>Importowanie konfiguracji polecenia przelewu ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób importowania konfiguracji raportowania elektronicznego płatności dla dostawcy. Jako przykładu użyto niemieckiego formatu poleceń przelewu zgodnego z normą ISO 20022. Procedura może być używana do innych dostępnych formatów raportowania elektronicznego. 

Zadanie zostało utworzone przy użyciu danych firmy demonstracyjnej DEMF, ale do wykonania zadania można użyć danych dowolnej firmy demonstracyjnej.

Jest to pierwsze z pięciu zadań, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.

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


