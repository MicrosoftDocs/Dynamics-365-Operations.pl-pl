---
title: Tworzenie obiektów kosztów
description: W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu do modułu Rachunek kosztów za pośrednictwem łącznika danych.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236801"
---
# <a name="create-cost-objects"></a>Tworzenie obiektów kosztów 

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu do modułu Rachunek kosztów za pośrednictwem łącznika danych. Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. 


## <a name="create-new-cost-objects"></a>Tworzenie nowych obiektów kosztów
1. Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary obiektów kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.
5. Wypełnij pole Opis.
6. Kliknij przycisk Zapisz.

## <a name="configure-the-data-connector"></a>Konfigurowanie łącznika danych
1. Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.
    * Wybierz centrum kosztu, aby zaimportować jego wymiar do modułu Rachunek kosztów.  
2. W polu Nazwa wymiaru wybierz wartość Centrum kosztu.
3. Kliknij przycisk OK.

## <a name="import-cost-centers"></a>Importowanie centrów kosztów
1. Kliknij opcję Importuj elementy członkowskie wymiaru.
2. Kliknij przycisk OK.

## <a name="view-the-imported-cost-centers"></a>Wyświetlanie zaimportowanych centrów kosztów
1. Kliknij opcję Wyświetl elementy członkowskie wymiaru.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]