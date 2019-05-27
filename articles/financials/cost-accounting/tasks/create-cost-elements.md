---
title: Tworzenie składników kosztu
description: Istnieje kilka sposobów tworzenia składników kosztów w module Rachunek kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bbaf4f7533d51d554d838e8e9e2aa05ca451298a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1543802"
---
# <a name="create-cost-elements"></a>Tworzenie składników kosztu 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Istnieje kilka sposobów tworzenia składników kosztów w module Rachunek kosztów. W tej procedurze pokazano, jak utworzyć składniki kosztów, importując konta główne za pośrednictwem łącznika danych. Dane wykorzystane do utworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Procedura dotyczy funkcji Rachunek kosztów dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="create-new-cost-elements"></a>Tworzenie nowych składników kosztów
1. Wybierz kolejno opcje Rachunek kosztów > Wymiary > Wymiary składników kosztów.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. W polu Łącznik danych dla elementów członkowskich wymiarów wprowadź lub wybierz wartość.
5. Wypełnij pole Opis.
6. Kliknij przycisk Zapisz.

## <a name="configure-the-data-connector"></a>Konfigurowanie łącznika danych
1. Kliknij opcję Konfiguruj dostawcę elementów członkowskich wymiarów.
2. W polu Plan kont wprowadź lub wybierz wartość.
    * Wybierz opcję Współdzielony, aby używać wspólnego planu kont.  
3. Kliknij przycisk Nowy.
4. Na liście oznacz wybrany wiersz.
    * Do kont można zastosować filtry, aby zostały spełnione żądane kryteria.  
5. W polu Z konta głównego wprowadź lub wybierz wartość.
6. W polu Do konta głównego wprowadź lub wybierz wartość.
7. Kliknij przycisk OK.

## <a name="import-main-accounts"></a>Importuj konta główne
1. Kliknij opcję Importuj elementy członkowskie wymiaru.
    * Konta główne zostaną zaimportowane do modułu Rachunek kosztów i będą używane jako składniki kosztu.  
2. Kliknij przycisk OK.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Wyświetlanie zaimportowanych kont jako składników kosztów
1. Kliknij opcję Wyświetl elementy członkowskie wymiaru.
    * Umożliwia wyświetlanie zaimportowanych kont księgowych jako składników kosztów w firmie, do których mogą spływać koszty.  

