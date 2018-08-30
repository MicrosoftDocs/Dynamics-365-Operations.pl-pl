---
title: "Konfigurowanie działań równoległych w przepływie pracy"
description: "Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 64cd387f8a6ab693d159cd659fca51fa6568ee39
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="configure-parallel-activities-in-a-workflow"></a>Konfigurowanie działań równoległych w przepływie pracy

[!include [banner](../includes/banner.md)]

Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy.

Działanie równoległe składa się z odgałęzień przepływu pracy, które są uruchomione w tym samym czasie.

## <a name="name-a-parallel-activity"></a>Nazywanie działania równoległego
Wykonaj następujące kroki, aby nazwać działanie równoległe.
1.  Kliknij działanie równoległe prawym przyciskiem myszy i wybierz polecenie **Właściwości**, aby otworzyć formularz **Właściwości**.
2.  W lewym okienku kliknij przycisk **Ustawienia podstawowe**.
3.  W polu **Nazwa** wprowadź unikatową nazwę działania równoległego.
4.  Kliknij przycisk **Zamknij**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Konfigurowanie odgałęzień działania równoległego
Wykonaj następujące kroki, aby dodać i skonfigurować gałęzie działania równoległego.
1. Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.
2. Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie. Na poniższej ilustracji przedstawiono punkt wstawiania.![Punkt wstawiania](./media/workflow_insertionpoint.gif)

   |                                              <strong>Uwaga</strong>                                               |
   |------------------------------------------------------------------------------------------------------------------|
   | Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie. |


3. Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzienia równoległego](configure-parallel-branch-workflow.md).






