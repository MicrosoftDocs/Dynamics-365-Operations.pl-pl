---
title: Sprawdzanie poprawności niestandardowego certyfikatu NF-e
description: Ten temat zawiera informacje dotyczące włączania i używania niestandardowego certyfikatu NF-e.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: f13e8b8229bbd9e174e5bde7858a468048ba309b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990093"
---
# <a name="nf-e-custom-certificate-validation"></a>Sprawdzanie poprawności niestandardowego certyfikatu NF-e

[!include [banner](../includes/banner.md)]

Po włączeniu funkcji weryfikacji niestandardowego certyfikatu NF-e niestandardowe sprawdzanie poprawności umożliwia połączenie z usługami sieci Web. To połączenie jest wymagane do przesyłania dokumentu NF-e i uzyskania autoryzacji od SEFAZ.

Właściwość **Cel uwierzytelnienie serwera** z certyfikatu V5 jest wystawiana przez brazylijski główny urząd certyfikacji. Ta właściwość jest domyślnie wyłączona i należy ją włączyć ręcznie. W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną. Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane. Ma to również wpływ na możliwość wydawania dokumentów NF-e w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).

Ta aktualizacja umożliwia rozwiązanie alternatywne dotyczące sprawdzania poprawności certyfikatów, co oznacza, że można ustanowić bezpieczną komunikację.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]