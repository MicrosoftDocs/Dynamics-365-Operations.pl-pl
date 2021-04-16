---
title: Sprawdzanie poprawności niestandardowego certyfikatu NF-e
description: Ten temat zawiera informacje dotyczące włączania i używania niestandardowego certyfikatu NF-e.
author: gionoder
ms.date: 10/06/2020
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
ms.openlocfilehash: 895513f51798a797ebf59f8a5be4f5cde006726d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813975"
---
# <a name="nf-e-custom-certificate-validation"></a>Sprawdzanie poprawności niestandardowego certyfikatu NF-e

[!include [banner](../includes/banner.md)]

Po włączeniu funkcji weryfikacji niestandardowego certyfikatu NF-e niestandardowe sprawdzanie poprawności umożliwia połączenie z usługami sieci Web. To połączenie jest wymagane do przesyłania dokumentu NF-e i uzyskania autoryzacji od SEFAZ.

Właściwość **Cel uwierzytelnienie serwera** z certyfikatu V5 jest wystawiana przez brazylijski główny urząd certyfikacji. Ta właściwość jest domyślnie wyłączona i należy ją włączyć ręcznie. W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną. Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane. Ma to również wpływ na możliwość wydawania dokumentów NF-e w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).

Ta aktualizacja umożliwia rozwiązanie alternatywne dotyczące sprawdzania poprawności certyfikatów, co oznacza, że można ustanowić bezpieczną komunikację.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]