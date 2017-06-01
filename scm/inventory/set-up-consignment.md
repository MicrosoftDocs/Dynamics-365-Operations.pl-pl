---
title: Konfigurowanie konsygnacji
description: "W tym temacie wyjaśniono sposób konfigurowania operacji konsygnacji przychodzącej dla zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b8692a3033cd665402721ea18ba8c28557c049de
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-consignment"></a>Konfigurowanie konsygnacji

[!include[banner](../includes/banner.md)]


W tym temacie wyjaśniono sposób konfigurowania operacji konsygnacji przychodzącej dla zapasów. 

Zapasy konsygnacyjne to zapasy, których właścicielem jest dostawca, ale są one przechowywane Twojej siedzibie. Gdy masz wszystko przygotowane do zużycia lub wykorzystania zapasów, przejmujesz ich własność. W tym temacie opisano konfigurację niezbędną do włączenia procesów konsygnacji. Aby uzyskać więcej informacji o procesach konsygnacji, zobacz [Konsygnacja](consignment.md).

## <a name="inventory-owners"></a>Właściciele zapasów
Aby zarejestrować fizyczne przychodzące zapasy konsygnacyjne, należy zdefiniować właściciela będącego dostawcą. Służy do tego strona **Właściciel zapasów**. Wybranie opcji **Konto dostawcy** spowoduje wygenerowanie wartości domyślnych dla pól **Nazwa** i **Właściciel**. Wartość w polu **Właściciel** będzie widoczna dla dostawcy, więc warto ją zmienić, jeśli nazwy kont dostawców przechowywane w firmowych systemach są trudne do rozpoznania przez osoby zewnętrzne. Istnieje możliwość edytowania pola **Właściciel**, ale tylko do momentu zapisania rekordu **Właściciel zapasów**. W polu **Nazwa** jest wprowadzana nazwa strony, z którą jest skojarzone konto dostawcy, i nie można jej zmienić. 

[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Grupa wymiarów śledzenia
Towary, które mają być używane w procesach konsygnacji, muszą być powiązane z **grupą wymiarów śledzenia**, która w wymiarze **Właściciel** ma ustawioną wartość **Aktywny**. Wymiar Właściciel zawsze ma zaznaczone opcje **Magazyn fizyczny** i **Magazyn finansowy**. Opcja **Plan zapotrzebowania wg wymiaru** nigdy nie jest zaznaczona. 

[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Arkusz zmian własności zapasów
Arkusz **Zmiana własności zapasów** służy do rejestrowania przeniesienia własności zapasów konsygnacyjnych z dostawcy na firmę, która je zużyje. Podobnie jak każdy arkusz magazynowy, musi być identyfikowany za pomocą nazwy arkusza magazynowego. Nazwy te są tworzone na stronie **Nazwy arkuszy magazynowych**, a w ustawieniu **Typ arkusza** trzeba zaznaczyć wartość **Zmiana własności**. 

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Współpraca z dostawcami w procesach konsygnacji
Jeśli dostawcy używają interfejsu współpracy z dostawcami, mogą w nim monitorować zużywanie zapasów w oddziale Twojej firmy. Aby uzyskać więcej informacji o konfigurowaniu dostawców do używania portalu współpracy z dostawcami, zobacz [Konfiguracja zabezpieczeń dla użytkowników portalu współpracy z dostawcami](../procurement/configure-security-vendor-portal-users.md).




