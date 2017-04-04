---
title: "Konfigurowanie równoległego działania przepływu pracy"
description: "Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 818fb054742b935d002a7341e54a37eca0bb4761
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Konfigurowanie równoległego działania przepływu pracy

Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.

Działanie równoległe składa się z odgałęzień przepływu pracy, które są uruchomione w tym samym czasie.

## <a name="name-a-parallel-activity"></a>Nazywanie działania równoległego
Wykonaj następujące kroki, aby nazwać działanie równoległe.
1.  Działanie równoległe kliknij prawym przyciskiem myszy, a następnie kliknij **właściwości** otworzyć **właściwości** formularza.
2.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
3.  W polu **Nazwa** wprowadź unikatową nazwę działania równoległego.
4.  Kliknij przycisk **Zamknij**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurowanie odgałęzień działania równoległego
Wykonaj następujące kroki, aby dodać i skonfigurować gałęzie działania równoległego.
1.  Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.
2.  Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie. Na poniższej ilustracji przedstawiono punkt wstawiania.![Punkt wstawiania](./media/workflow_insertionpoint.gif)
    | **Uwaga **                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie. |

3.  Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzienia równoległego](http://axhelp.dynamics.com/en/wiki/configure-a-parallel-branch/).




