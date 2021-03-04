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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87f93fd7c1c42045274d6b89847b27e93614d9a4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446935"
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