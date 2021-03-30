---
title: Omówienie planowania ładunków przy użyciu konsolidacji w centrum
description: W tym artykule opisano funkcjonalność konsolidowania wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87b599c953244109b56958c0fe02deedfa252973
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205209"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Omówienie planowania ładunków przy użyciu konsolidacji w centrum

[!include [banner](../includes/banner.md)]

W tym artykule opisano funkcjonalność konsolidowania wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu.

Może być przydatne skonsolidowanie wysyłek w centrum, gdy towary są dostarczane z różnych magazynów do tego samego odbiorcy albo od wielu dostawców do tego samego magazynu.

## <a name="building-loads"></a>Kompilowanie ładunków
Zanim będzie można używać konsolidacji w centrum, należy włączyć opcję **Planowanie w drodze** na karcie **Parametry zarządzania transportem**. Należy również utworzyć centra, w których będzie następowała konsolidacja. Poniższy diagram przedstawia przykład konsolidacji w centrum. W tym przypadku zamówienia sprzedaży z różnych magazynów trafiają do tego samego odbiorcy. Podstawowe ładunki są tworzone na podstawie zamówień sprzedaży w zwykły sposób, za pomocą strony **Warsztat planowania wysyłki ładunku**. Aby skonsolidować dwa ładunki w centrum, zanim zostaną dostarczone do odbiorcy, na stronie **Warsztat planowania wysyłki ładunku** w polu **Transport** zaznacz opcję **Konsolidacja centrum**. Po wybraniu odpowiedniego centrum dla każdego ładunku ładunki będą miały centrum jako miejsce docelowe „dostawy”. Ponadto istnieją dwa „wiersze wniosku o transport” w sekcji **Popyt i podaż** na stronie **Warsztat planowania wysyłki ładunku**. Następnie można dodać te dwa wiersze do nowego ładunku. Nowy ładunek będzie zawierał oba wiersze zamówienia sprzedaży oraz będzie miał centrum jako adres „odbioru”, a odbiorcę A jako miejsce docelowe „dostawy”. Następnie wszystkie trzy ładunki są gotowe do ustawienia stawek i wyznaczenia tras jak każdy inny ładunek. Dla każdego ładunku można wybrać dowolnego przewoźnika proponowanego przez system. [![Konsolidacja centrum](./media/hubconsol.jpg)](./media/hubconsol.jpg) Tej samej metody można używać do konsolidowania ładunków dla wielu zamówień przeniesienia. W takim przypadku odbiorca A na powyższym diagramie jest magazynem. Alternatywnie można konsolidować ładunki dla wielu zamówień zakupu, jeżeli ładunki są dostarczane od różnych dostawców do tego samego magazynu. Można mieć więcej niż jedno centrum konsolidacji oraz konsolidować w wielu centrach w przypadku większej ilości ładunków pochodzących z różnych magazynów. Gdy skompilujesz podstawowe ładunki i włączysz opcję konsolidacji w centrum, nowe ładunki tworzysz przy użyciu wierszy wniosku o transport skonsolidowany. Następnie ustawiasz stawki i rozsyłasz ładunki.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]