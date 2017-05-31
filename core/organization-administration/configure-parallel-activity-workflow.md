---
title: "Konfigurowanie działania równoległego w przepływie pracy"
description: "Aby skonfigurować działanie równoległe, należy wykonać następujące procedury w edytorze przepływu pracy."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4c2f98803164d5c761d2089152c077cfb9e83c43
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Konfigurowanie działania równoległego w przepływie pracy

[!include[banner](../includes/banner.md)]


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
1.  Kliknij dwukrotnie działanie równoległe, aby wyświetlić jego odgałęzienia.
2.  Aby dodać gałąź, przeciągnij element **Gałąź** z obszaru **Elementy przepływu pracy** na punkt wstawiania na kanwie. Na poniższej ilustracji przedstawiono punkt wstawiania.![Punkt wstawiania](./media/workflow_insertionpoint.gif)
    | **Uwaga**                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | Kolejność odgałęzień jest nieważna, ponieważ wszystkie gałęzie działania równoległego są uruchamiane jednocześnie. |

3.  Aby skonfigurować poszczególne gałęzie, zobacz [Konfigurowanie odgałęzienia równoległego](configure-parallel-branch-workflow.md).






