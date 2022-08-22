---
title: Przetwarzanie przychodzących dokumentów elektronicznych
description: Ten artykuł zawiera omówienie przetwarzania przychodzących dokumentów elektronicznych.
author: gionoder
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 554bc8fde3b2135eb878d885541c76ecd6d66493
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277310"
---
# <a name="processing-of-incoming-electronic-documents"></a>Przetwarzanie przychodzących dokumentów elektronicznych

[!include [banner](../includes/banner.md)]

Przychodzące dokumenty elektroniczne, takie jak faktury elektroniczne dostawcy, można importować i przetwarzać na dwa sposoby:

- Pliki są pobierane z kanałów zewnętrznych i przekazywane bezpośrednio do podłączonej aplikacji. Tam przechodzą dodatkowe przekształcenia, a następnie są importowane do bazy danych.
- Pliki poddane wstępnemu przetwarzaniu w usłudze fakturowania elektronicznego, a następnie są przekazywane do podłączonej aplikacji.

Fakturowanie elektroniczne obsługuje dwa kanały dokumentów przychodzących: e-mail i foldery firmy Microsoft SharePoint.

Istnieją typy ustawień TWP, które określają, czy dokumenty podlegają przetwarzaniu wstępnemu, czy są przekazywane bezpośrednio do połączonej aplikacji:

- **Kanał danych** — System przekaże dokument bezpośrednio do połączonej aplikacji.
- **Kanał danych z potokiem przetwarzania** — istnieje możliwość skonfigurowania dodatkowych akcji, które będą uruchamiane przed przekazem dokumentu do połączonej aplikacji.

Aby uzyskać informacje dotyczące konfigurowania scenariuszy przetwarzania przychodzących dokumentów elektronicznych dla różnych kanałów, zobacz temat [Konfigurowanie kanału poczty e-mail](e-invoicing-configure-email.md) i [Konfigurowanie kanału SharePoint](e-invoicing-configure-sharepoint-channel.md).
