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
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446733"
---
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="b176a-103">Sprawdzanie poprawności niestandardowego certyfikatu NF-e</span><span class="sxs-lookup"><span data-stu-id="b176a-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b176a-104">Po włączeniu funkcji weryfikacji niestandardowego certyfikatu NF-e niestandardowe sprawdzanie poprawności umożliwia połączenie z usługami sieci Web.</span><span class="sxs-lookup"><span data-stu-id="b176a-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="b176a-105">To połączenie jest wymagane do przesyłania dokumentu NF-e i uzyskania autoryzacji od SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="b176a-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="b176a-106">Właściwość **Cel uwierzytelnienie serwera** z certyfikatu V5 jest wystawiana przez brazylijski główny urząd certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="b176a-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="b176a-107">Ta właściwość jest domyślnie wyłączona i należy ją włączyć ręcznie.</span><span class="sxs-lookup"><span data-stu-id="b176a-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="b176a-108">W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną.</span><span class="sxs-lookup"><span data-stu-id="b176a-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="b176a-109">Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane.</span><span class="sxs-lookup"><span data-stu-id="b176a-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="b176a-110">Ma to również wpływ na możliwość wydawania dokumentów NF-e w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).</span><span class="sxs-lookup"><span data-stu-id="b176a-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="b176a-111">Ta aktualizacja umożliwia rozwiązanie alternatywne dotyczące sprawdzania poprawności certyfikatów, co oznacza, że można ustanowić bezpieczną komunikację.</span><span class="sxs-lookup"><span data-stu-id="b176a-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>


