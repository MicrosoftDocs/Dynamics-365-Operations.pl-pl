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
ms.openlocfilehash: 9aca699283a9de6ea551bd02184498aed88143e9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991647"
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