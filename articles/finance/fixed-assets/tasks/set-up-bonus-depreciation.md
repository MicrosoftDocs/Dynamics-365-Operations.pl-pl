---
title: Konfigurowanie podwyższenia amortyzacji
description: W tej procedurze pokazano, jak utworzyć specjalny odpis amortyzacyjny i skojarzyć go z księgą środków trwałych.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad1b7f584d2b2a63dba5f8519ada9d89d6265e7b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815627"
---
# <a name="set-up-bonus-depreciation"></a>Konfigurowanie podwyższenia amortyzacji

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]