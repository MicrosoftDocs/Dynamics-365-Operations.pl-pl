---
title: Tworzenie obiektów kosztów
description: W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f63827977f080aa78fb385c60f757ad6b710005
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841256"
---
# <a name="create-cost-objects"></a>Tworzenie obiektów kosztów 

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia obiektów kosztów, importując wymiar finansowy centrum kosztu programu Dynamics 365 for Finance and Operations Enterprise Edition do modułu Rachunek kosztów za pośrednictwem łącznika danych. Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Dynamics 365 for Operations w wersji 1611.


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

