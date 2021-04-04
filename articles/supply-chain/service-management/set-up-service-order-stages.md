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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9774d5f4e97d3f768366ba552e5928929bacf508
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470936"
---
# <a name="set-up-service-order-stages"></a>Ustawianie etapów zlecenia serwisowego 

[!include [banner](../includes/banner.md)]


1.  Przejdź do **Zarządzanie serwisem** \> **Ustawienia** \> **Zlecenia serwisowe** \> **Etapy serwisu**.

2.  Wybierz pozycję **Nowy**, aby utworzyć nowy zapis.

3.  W polach **Etap serwisu** i **Opis** wprowadź identyfikator i opis etapu serwisu.

4.  Wybierz odpowiednie parametry etapu.

5.  Wybierz etap nadrzędny dla bieżącego etapu lub pozostaw pole **Nadrzędne** puste, jeśli ten etap jest etapem początkowym w konfiguracji etapów.


> [!NOTE]
> <P>Po zapisaniu etapu nie można zmodyfikować pola <STRONG>Nadrzędne</STRONG>. Zamiast tego należy usunąć rekord i utworzyć go ponownie, dokonując innego wyboru w polu <STRONG>Nadrzędne</STRONG>.</P>
> <P>Ponadto można utworzyć tylko jeden etap z pustym polem <STRONG>Nadrzędne</STRONG>. Oznacza to, że jest dozwolony tylko jeden etap początkowy.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]