---
title: Wystąpił błąd podczas uruchamiania wbudowanego aparatu planowania głównego
description: Podczas uruchamiania przestarzałego wbudowanego mechanizmu planowania głównego pojawia się komunikat o błędzie.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294156"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Wystąpił błąd podczas uruchamiania wbudowanego aparatu planowania głównego

Kod błędu: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Objawy

Podczas uruchamiania planowania nadrzędnego przy użyciu przestarzałego wbudowanego mechanizmu planowania nadrzędnego pojawia się następujący komunikat o błędzie:

> Ten komunikat o błędzie jest wyświetlany, ponieważ wbudowany główny aparat planowania był używany w scenariuszach obsługiwanych przez optymalizację planowania. Należy teraz przeprowadzić migrację do optymalizacji planowania, ponieważ bieżące wbudowane planowanie główne zostanie wycofane. Należy zauważyć, że ten przebieg planowania głównego zakończył się pomyślnie. Jeśli migracja jest silnie uzależniona od oczekujących funkcji, można zażądać wyjątku od dalszego korzystania z wbudowanego głównego silnika planowania. Wypełnij poniższy kwestionariusz, aby rozpocząć i w razie potrzeby poprosić o wyjątek od migracji do optymalizacji planowania. [Kwestionariusz migracji i wyjątków w optymalizacji planowania](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Powód

Jeśli prowadzisz planowanie i nie używasz funkcji kontroli produkcji, powinieneś rozważyć migrację do optymalizacji planowania. Wbudowany aparat planowania głównego jest wycofywany. Dlatego, jeśli chcesz nadal używać go bez otrzymywania komunikatu o błędzie, musisz ubiegać się o wyjątek od firmy Microsoft.

## <a name="resolution"></a>Rozwiązanie

Aby uzyskać więcej informacji na temat migracji do optymalizacji planowania lub ubiegania się o wyjątek umożliwiający dalsze korzystanie z przestarzałego wbudowanego mechanizmu planowania, patrz [Migracja do optymalizacji planowania w ramach planowania głównego](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
