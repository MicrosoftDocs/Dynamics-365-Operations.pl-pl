---
title: Transakcje subskrypcji kredytu
description: Ten temat opisuje, jak kredytować transakcje opłat subskrypcji.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c4cbc3cd5deff709ac0818358dcc87fa69a7d872
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435342"
---
# <a name="credit-subscription-transactions"></a>Transakcje subskrypcji kredytu 

[!include [banner](../includes/banner.md)]


## <a name="credit-subscription-transactions"></a>Transakcje subskrypcji kredytu

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Subskrypcje serwisowe** \> **Wszystkie subskrypcje serwisu**.

2.  Zaznacz subskrypcję połączoną z transakcją subskrypcji, dla której ma zostać utworzona faktura korygująca.

3.  Kliknij kartę **Analizuj**, a następnie w okienku akcji kliknij przycisk **Transakcje opłat**.

4.  W formularzu **Transakcje opłat** zaznacz transakcję, dla której ma zostać utworzona faktura korygująca.

5.  Kliknij kolejno opcje **Funkcje** \> **Wybierz do faktury korygującej**

6.  W formularzu **Wybierz do faktury korygującej** wybierz transakcję, dla której chcesz utworzyć uznanie, i kliknij przycisk **OK**.


> [!NOTE]
> <P>Podczas tworzenia faktury korygującej należy upewnić się, że wybrano opcję <STRONG>Faktury korygujące</STRONG>. Znajduje się ona na liście <STRONG>Metoda fakturowania</STRONG> w oknie dialogowym <STRONG>Utwórz fakturę</STRONG>.</P>

Jeśli pole **Wycofaj naliczenia przy korekcie** w formularzu **Parametry modułu Zarządzanie serwisem** ma wartość **Ręcznie**, przed utworzeniem propozycji faktury korygującej dla transakcji należy wycofać poszczególne transakcje z naliczonym przychodem.

## <a name="see-also"></a>Informacje dodatkowe

[Fakturowanie transakcji subskrypcji](invoice-subscription-transactions.md)


 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]