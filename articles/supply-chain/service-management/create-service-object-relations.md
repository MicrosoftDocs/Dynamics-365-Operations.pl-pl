---
title: Tworzenie relacji przedmiotów serwisu
description: W tym artykule opisano sposób tworzenia relacji przedmiotów serwisu dla umowy serwisowej i zlecenia serwisowego.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4d9424b5678a6f37d46203e5d4e359b020fda7a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016978"
---
# <a name="create-service-object-relations"></a>Tworzenie relacji przedmiotów serwisu 

[!include [banner](../includes/banner.md)]


W tym artykule opisano sposób tworzenia relacji przedmiotów serwisu dla umowy serwisowej i zlecenia serwisowego. Podczas tworzenia relacji przedmiotów serwisu przedmiot serwisu jest łączony z umową serwisową lub zleceniem serwisowym. Gdy klient zażąda usługi dotyczącej pozycji, która jest przedmiotem serwisu, możesz wybrać przedmiot serwisu z listy relacji przedmiotów serwisu.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Tworzenie relacji przedmiotów serwisu dla umowy serwisowej

Aby utworzyć relację przedmiotów serwisu dla umowy serwisowej, wykonaj następujące czynności:

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Umowy serwisowe** \> **Umowy serwisowe**.

2.  Z listy **Umowy serwisowe** wybierz istniejącą umowę serwisową lub kliknij opcję **Nowy**, aby utworzyć nową umowę serwisową.

3.  W formularzu **Umowy serwisowe** w **okienku akcji** na karcie **Umowa serwisowa** w grupie **Relacje** kliknij opcję **Przedmioty serwisu**.

4.  W formularzu **Przedmioty serwisu** kliknij opcję **Nowy**, a następnie wybierz przedmiot serwisu dla tej umowy serwisowej.

5.  Aby przypisać szablon listy składowej (BOM) do umowy serwisowej, kliknij opcję **Funkcje** i wybierz opcję **Dołącz szablon BOM**. W formularzu **Wybierz szablon BOM** w polu **Szablon BOM** wybierz szablon. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Tworzenie relacji przedmiotów serwisu dla zlecenia serwisowego

Aby utworzyć relację przedmiotów serwisu dla zlecenia serwisowego, wykonaj następujące czynności:

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Z listy **Zlecenia serwisowe** wybierz istniejące zlecenie serwisowe lub utwórz nowe.

3.  W formularzu **Zlecenia serwisowe** w **okienku akcji** na karcie **Zlecenie serwisowe** w grupie **Relacje** kliknij opcję **Przedmioty serwisu**.

4.  W formularzu **Przedmioty serwisu** kliknij opcję **Nowy**, a następnie wybierz przedmiot serwisu dla tego zlecenia serwisowego.

5.  Aby przypisać szablon BOM do umowy serwisowej, kliknij opcję **Funkcje** i wybierz opcję **Dołącz szablon BOM**. W formularzu **Wybierz szablon BOM** w polu **Szablon BOM** wybierz szablon. 


## <a name="see-also"></a>Informacje dodatkowe

[Omówienie przedmiotów serwisu](service-objects.md)

[Relacje przedmiotów serwisu](service-object-relations.md)

[Szablony BOM](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]