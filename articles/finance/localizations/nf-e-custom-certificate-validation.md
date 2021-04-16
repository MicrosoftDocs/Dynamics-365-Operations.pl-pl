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
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="7490f-103">Sprawdzanie poprawności niestandardowego certyfikatu NF-e</span><span class="sxs-lookup"><span data-stu-id="7490f-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7490f-104">Po włączeniu funkcji weryfikacji niestandardowego certyfikatu NF-e niestandardowe sprawdzanie poprawności umożliwia połączenie z usługami sieci Web.</span><span class="sxs-lookup"><span data-stu-id="7490f-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="7490f-105">To połączenie jest wymagane do przesyłania dokumentu NF-e i uzyskania autoryzacji od SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="7490f-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="7490f-106">Właściwość **Cel uwierzytelnienie serwera** z certyfikatu V5 jest wystawiana przez brazylijski główny urząd certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="7490f-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="7490f-107">Ta właściwość jest domyślnie wyłączona i należy ją włączyć ręcznie.</span><span class="sxs-lookup"><span data-stu-id="7490f-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="7490f-108">W niektórych przypadkach automatyczna aktualizacja certyfikatów może przełączyć tę właściwość na wyłączoną.</span><span class="sxs-lookup"><span data-stu-id="7490f-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="7490f-109">Jeśli tak się stanie, wpływa to na połączenie TLS i nie jest już ono zaufane.</span><span class="sxs-lookup"><span data-stu-id="7490f-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="7490f-110">Ma to również wpływ na możliwość wydawania dokumentów NF-e w środowiskach produkcyjnych dla Stanów Minas Gerais (MG) i Paraná (PR).</span><span class="sxs-lookup"><span data-stu-id="7490f-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="7490f-111">Ta aktualizacja umożliwia rozwiązanie alternatywne dotyczące sprawdzania poprawności certyfikatów, co oznacza, że można ustanowić bezpieczną komunikację.</span><span class="sxs-lookup"><span data-stu-id="7490f-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]