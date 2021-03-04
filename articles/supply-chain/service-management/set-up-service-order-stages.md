---
title: Ustawianie etapów zlecenia serwisowego
description: Można ustawić etapy zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86d60a67b60b1bd3a13666b35f729f88ecfee3d3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434897"
---
# <a name="set-up-service-order-stages"></a>Ustawianie etapów zlecenia serwisowego 

[!include [banner](../includes/banner.md)]


1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Etapy serwisu**.

2.  Naciśnij kombinację klawiszy CTRL+N, aby utworzyć nowy rekord.

3.  W polach **Etap serwisu** i **Opis** wprowadź identyfikator i opis etapu serwisu.

4.  Wybierz odpowiednie parametry etapu.

5.  Wybierz etap nadrzędny dla bieżącego etapu lub pozostaw pole **Nadrzędne** puste, jeśli ten etap jest etapem początkowym w konfiguracji etapów.


> [!NOTE]
> <P>Po zapisaniu etapu nie można zmodyfikować pola <STRONG>Nadrzędne</STRONG>. Zamiast tego należy usunąć rekord i utworzyć go ponownie, dokonując innego wyboru w polu <STRONG>Nadrzędne</STRONG>.</P>
> <P>Ponadto można utworzyć tylko jeden etap z pustym polem <STRONG>Nadrzędne</STRONG>. Oznacza to, że jest dozwolony tylko jeden etap początkowy.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]