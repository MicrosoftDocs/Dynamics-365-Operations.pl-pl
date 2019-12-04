---
title: Automatyczne tworzenie zleceń serwisowych
description: Zlecenia serwisowe można tworzyć dla jednej lub kilku umów serwisowych.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d91ccc6a3ebaff220c8a876944b90d910399660
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814036"
---
# <a name="create-service-orders-automatically"></a>Automatyczne tworzenie zleceń serwisowych    

[!include [banner](../includes/banner.md)]


Zlecenia serwisowe można tworzyć dla jednej lub kilku umów serwisowych. Utworzone zlecenia serwisowe można wyświetlić w formularzu **Zlecenia serwisowe**.

Zlecenia serwisowe są tworzone tylko dla ważnego okresu umowy serwisowej. Jeśli ramy czasowe określone w formularzu **Utwórz zlecenia serwisowe** wykraczają przed datę rozpoczęcia lub za datę zakończenia umowy serwisowej, zlecenia serwisowe są tworzone tylko dla tej części ram czasowych, która mieści się w granicach czasowych umowy serwisowej.

Podczas tworzenia zleceń serwisowych ręcznie lub automatycznie z poziomu wiersza umowy serwisowej zlecenie musi się mieścić w granicach przedziału czasu określonego przez daty początkową i końcową ustawione dla wiersza, chyba że dla wiersza nie określono daty końcowej.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Automatyczne tworzenie zleceń serwisowych dla umowy serwisowej

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Wybierz umowę serwisową.

3.  Kliknij kartę **Dostarcz**, a następnie kliknij opcję **Planowane zlecenia serwisowe**.

4.  Określ daty w polach **Od dnia** i **Do dnia**, aby zdefiniować okres serwisu.

5.  Zaznacz pole wyboru **Pokaż dziennik informacyjny**, aby wyświetlić listę utworzonych zleceń serwisowych.

6.  Wybierz typy transakcji w grupie pól **Uwzględnij typy transakcji**. Typy transakcji reprezentują wiersze utworzone w umowie serwisowej, a każdy wybrany typ transakcji powoduje wygenerowanie kilku zleceń serwisowych, w zależności od ram czasowych serwisu określonych w wierszu umowy serwisowej.

7.  Aby utworzyć wszelkie brakujące zlecenia serwisowe w ramach ciągłej serii zleceń serwisowych, zaznacz pole wyboru **Ciągłe**.

8.  Kliknij przycisk **OK**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Automatyczne tworzenie zleceń serwisowych dla kilku umów serwisowych

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Okresowe** \> **Zlecenia serwisowe** \> **Utwórz zlecenia serwisowe**.

2.  Kliknij przycisk **Wybierz** i dodaj lub usuń kryteria używane do tworzenia zleceń serwisowych.

3.  Kliknij przycisk **OK**.

## <a name="see-also"></a>Informacje dodatkowe

[Zlecenia serwisowe](service-orders.md)

[Automatyczne tworzenie zleceń serwisowych](auto-create-service-orders.md)

  


