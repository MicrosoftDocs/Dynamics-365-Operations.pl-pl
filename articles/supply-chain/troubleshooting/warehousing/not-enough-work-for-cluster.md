---
title: Nie znaleziono wystarczającej ilości pracy dla grupy po skonfigurowaniu profilu
description: W przypadku skonfigurowania profilu grupy może zostać wyświetlony komunikat o błędzie informujący o niewystarczającej pracy. Edytuj profil i ustaw wartość Aktywuj stanowiska na wartość Nie.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477274"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Nie znaleziono wystarczającej ilości pracy dla grupy podczas używania pobierania grupy kierowanej przez system

## <a name="symptoms"></a>Objawy

Używając procesu *Pobieranie dla grupy sterowane przez system*, jeśli skonfigurujesz profil grupy, w którym można odebrać na przykład 10 stanowisk, proces działa zgodnie według planu, kiedy jest wystarczająco pracy dla 10 stanowisk odbioru. Jeśli jednak do pobrania jest tylko osiem stanowisk, jest wyświetlany następujący komunikat o błędzie:

> Nie można znaleźć wystarczającej ilości pracy dla grupy.

## <a name="resolution"></a>Rozwiązanie

Aby rozwiązać ten problem, edytuj profil grupy i w opcji **Aktywuj stanowiska** określ wartość *Nie*.
