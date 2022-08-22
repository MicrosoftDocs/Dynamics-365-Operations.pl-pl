---
title: Walidacja niestandardowego certyfikatu NF-e
description: Ten artykuł zawiera informacje dotyczące włączania i używania niestandardowego certyfikatu NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f78fdbd133aecaf9dbf8abe0006abd6deb1b1b15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288553"
---
# <a name="nf-e-custom-certificate-validation"></a>Walidacja niestandardowego certyfikatu NF-e

[!include [banner](../includes/banner.md)]

Właściwość **Cel uwierzytelniania serwera** w certyfikatach wydanych przez Brazilian Root Certificate Authority jest domyślnie wyłączona i musi być włączona ręcznie. W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną. Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane. Ma to również wpływ na możliwość wydawania wzoru brazylijskich dokumentów fiskalnych 55 (NF-e) w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).

Aby włączyć poprawkę **Weryfikacji niestandardowego certyfikatu NF-e**, przejdź do **zarządzania funkcjami**. Funkcja ta umożliwia alternatywne rozwiązanie dla walidacji certyfikatów V5 i V10 oraz pozwala na nawiązanie zaufanego połączenia z serwisami internetowymi, które jest wymagane do bezpiecznego przesyłania NF-e i otrzymania autoryzacji z SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
