---
title: Konfigurowanie działań równoległych w przepływie pracy
description: Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1a47857cbe65c00ad678b2b0372c642abf01b41
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747838"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Konfigurowanie działań równoległych w przepływie pracy

[!include [banner](../includes/banner.md)]

Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.

Działanie równoległe składa się z odgałęzień przepływu pracy, które są uruchomione w tym samym czasie.

## <a name="name-a-parallel-activity"></a>Nazywanie działania równoległego

Wykonaj następujące kroki, aby nazwać działanie równoległe.

1. Kliknij działanie równoległe prawym przyciskiem myszy i wybierz polecenie **Właściwości**, aby otworzyć formularz **Właściwości**.
2. W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
3. W polu **Nazwa** wprowadź unikatową nazwę działania równoległego.
4. Kliknij przycisk **Zamknij**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurowanie odgałęzień działania równoległego

Wykonaj następujące kroki, aby dodać i skonfigurować gałęzie działania równoległego.

1. Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.
2. Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie. Na poniższej ilustracji przedstawiono punkt wstawiania.

    ![Punkt wstawiania](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie.

3. Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzień równoległych w przepływie pracy](configure-parallel-branch-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]