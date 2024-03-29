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
ms.openlocfilehash: 054d62e2ff094aee987f8c6e04e2f2e173da633d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068770"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Konfigurowanie działań równoległych w przepływie pracy

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

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

    ![Punkt wstawiania.](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie.

3. Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzień równoległych w przepływie pracy](configure-parallel-branch-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]