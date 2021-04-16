---
title: Tworzenie składników kosztu
description: Istnieje kilka sposobów tworzenia składników kosztów w module Rachunek kosztów.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c4c1e2aee7ba98c1cca378286afb643eaca1600
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810085"
---
# <a name="create-cost-elements"></a>Tworzenie składników kosztu 

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]