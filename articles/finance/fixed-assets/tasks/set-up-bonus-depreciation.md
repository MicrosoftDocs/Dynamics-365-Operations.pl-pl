---
title: Konfigurowanie podwyższenia amortyzacji
description: W tej procedurze pokazano, jak utworzyć specjalny odpis amortyzacyjny i skojarzyć go z księgą środków trwałych.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788cddf4d822fe3d3d6a33e83d7b30f32f4b6b9c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179376"
---
# <a name="set-up-bonus-depreciation"></a>Konfigurowanie podwyższenia amortyzacji

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć specjalny odpis amortyzacyjny i skojarzyć go z księgą środków trwałych. Procedura korzysta z roli księgowego i danych firmy demonstracyjnej USMF.


## <a name="create-a-special-depreciation-allowance"></a>Tworzenie specjalnego odpisu amortyzacyjnego
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Specjalny odpis amortyzacyjny.
2. Kliknij przycisk Nowy.
3. W polu Specjalny odpis amortyzacyjny wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Wartość procentowa wpisz liczbę.
    * Jeśli nie wskazano wartości procentowej, ustaw kwotę.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Kojarzenie specjalnego odpisu amortyzacyjnego z księgą grupy środków trwałych
1. Wybierz kolejno opcje Środki trwałe > Ustawienia > Grupy środków trwałych.
2. Na liście zaznacz grupę środków trwałych skojarzoną ze specjalnym odpisem amortyzacyjnym.
3. Kliknij opcję Księgi.
4. Na liście zaznacz księgę skojarzoną ze specjalnym odpisem amortyzacyjnym.
5. Kliknij opcję Specjalny odpis amortyzacyjny.
6. Kliknij przycisk Nowy.
7. W polu Specjalny odpis amortyzacyjny wpisz lub wybierz wartość.
    * Domyślna wartość ustawienia Wartość procentowa lub Kwota pochodzi z konfiguracji specjalnego odpisu amortyzacyjnego.  
8. W polu Priorytet wprowadź liczbę.

