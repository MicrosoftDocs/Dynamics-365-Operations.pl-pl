---
title: Tworzenie modeli prognozy dla budżetów projektu
description: W tym temacie opisano sposób tworzenia modelu prognozy dla pozostałych budżetów.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321786"
---
# <a name="create-forecast-models-for-project-budgets"></a>Tworzenie modeli prognozy dla budżetów projektu 

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia modelu prognozy dla pozostałych budżetów. Projekt, dla którego obowiązuje kontrola budżetu używa dwóch typów budżetu: pierwotnego i pozostałego. Podczas tworzenia budżetu projektu należy określić modele prognoz pozostałego i pierwotnego budżetu, które zostały utworzone na stronie **Modele prognoz**. Budżety projektów oparte na określonych modelach są tworzone podczas zatwierdzania budżetu projektu.

> [!NOTE]
> Model prognozy używany do kontroli budżetu nie może mieć podmodelu ani służyć jako podmodel.

1. Wybierz pozycję **Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Prognozy**  > **Modele prognoz**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy model prognozy, a następnie wprowadź numer identyfikacyjny i nazwę nowego modelu. 
3. Ustaw opcję **Zatrzymano** na **Tak**, aby uniemożliwić wprowadzanie zmian w wierszach prognozy dla modelu prognozy. 
4. Jeśli wiersze prognozy, z którymi model jest skojarzony, muszą generować prognozy przepływów pieniężnych w księdze głównej, ustaw opcję **Uwzględnianie budżetów w prognozach przepływów pieniężnych** na **Tak**. 
5. Aby użyć daty projektu jako daty faktury, ustaw **datę faktury prognozy** na **Tak**. 
6. W polu **Typ budżetu** wybierz jeden z następujących typów modeli:

   - **Budżet pierwotny**: użyj kwot budżetu pierwotnego ustalonych podczas tworzenia i zatwierdzania początkowego budżetu.
   - **Pozostały budżet**: użyj kwot pozostałego budżetu w okresie użytkowania projektu. Salda w tym modelu prognozy są pomniejszone o rzeczywiste transakcje i powiększone lub pomniejszone o korekty budżetu.
   - **Przenieś na następny okres**: użyj kwot budżetu przeniesionego na późniejszy okres dla projektu. Przeniesienie na następny okres jest opcjonalnym procesem uruchamianym w celu przeniesienia niewykorzystanych kwot budżetu do innego roku obrachunkowego.

7. W razie potrzeby ustaw następujące opcje:

   - Włącz **datę faktury projektu**, aby użyć daty projektu jako daty faktury.
   - Włącz **prognozę przy użyciu PWT**, aby prognozować na podstawie pracy w toku (PWT), a następnie wybierz typ PWT. 
   - Możesz zachować domyślny **typ budżetu** jako **Brak** lub wprowadzić nowy typ. Typu budżetu nie można zmienić po zmianie rekordu.     
    > [!NOTE]
    > Zmiana domyślnego typu budżetu spowoduje, że wszystkie inne opcje staną się niedostępne dla aktualizacji i nie będzie można ponownie użyć tego modelu prognozy. 
   


 

