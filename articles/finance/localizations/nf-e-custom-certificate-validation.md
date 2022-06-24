---
title: Walidacja niestandardowego certyfikatu NF-e
description: Ten artykuł zawiera informacje dotyczące włączania i używania niestandardowego certyfikatu NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3d69aa9d6d0ce33fbed9ba1c7a7af441e14d0d07
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875912"
---
# <a name="nf-e-custom-certificate-validation"></a>Walidacja niestandardowego certyfikatu NF-e

[!include [banner](../includes/banner.md)]

Właściwość **Cel uwierzytelniania serwera** w certyfikatach wydanych przez Brazilian Root Certificate Authority jest domyślnie wyłączona i musi być włączona ręcznie. W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną. Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane. Ma to również wpływ na możliwość wydawania wzoru brazylijskich dokumentów fiskalnych 55 (NF-e) w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).

Aby włączyć poprawkę **Weryfikacji niestandardowego certyfikatu NF-e**, przejdź do **zarządzania funkcjami**. Funkcja ta umożliwia alternatywne rozwiązanie dla walidacji certyfikatów V5 i V10 oraz pozwala na nawiązanie zaufanego połączenia z serwisami internetowymi, które jest wymagane do bezpiecznego przesyłania NF-e i otrzymania autoryzacji z SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
