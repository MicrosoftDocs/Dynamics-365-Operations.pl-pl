---
title: Przetwarzanie przychodzących dokumentów elektronicznych
description: Ten artykuł zawiera omówienie przetwarzania przychodzących dokumentów elektronicznych.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: dec4c16c8ba9f0ba55f30f3944eff172cf9db724
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910016"
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
