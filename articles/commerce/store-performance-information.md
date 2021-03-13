---
title: Analiza wydajności sklepu
description: W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o efektywności działania sklepów na podstawie danych programu Dynamics 365 Commerce.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelReport, RetailChannelManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 57811
ms.assetid: 495a66f0-491a-4688-842d-51c33c37676f
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 4688d3268986a9ae6fb2c9601396b56aacf87a93
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009625"
---
# <a name="analyze-store-performance"></a><span data-ttu-id="6b9f8-103">Analizowanie wydajności sklepu</span><span class="sxs-lookup"><span data-stu-id="6b9f8-103">Analyze store performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6b9f8-104">W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o efektywności działania sklepów na podstawie danych programu Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6b9f8-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about store performance, based on your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="6b9f8-105">W ramach Retail użytkownicy mogą badać wydajność sklepu w czasie rzeczywistym na różnych poziomach hierarchii organizacyjnej przez wybrany okres. W tym celu należy otworzyć gotowy raport **Podsumowanie kanału** w dowolnym z następujących miejsc:</span><span class="sxs-lookup"><span data-stu-id="6b9f8-105">As part of Retail, users can study store performance in real time across different levels of the organization hierarchy over a selected period by opening the out-of-box **Channel summary** report from any of the following locations:</span></span>

- <span data-ttu-id="6b9f8-106">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport podsumowania kanału**</span><span class="sxs-lookup"><span data-stu-id="6b9f8-106">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel summary report**</span></span>
- <span data-ttu-id="6b9f8-107">Obszar roboczy **Finanse sklepu sieciowego** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Finanse sklepu sieciowego** &gt; **Raporty** &gt; **Raport podsumowania kanału**</span><span class="sxs-lookup"><span data-stu-id="6b9f8-107">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel summary report**</span></span>
- <span data-ttu-id="6b9f8-108">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport podsumowania kanału**</span><span class="sxs-lookup"><span data-stu-id="6b9f8-108">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel summary report**</span></span>

<span data-ttu-id="6b9f8-109">Ten raport zawiera migawkę poniższych podsumowań w ramach wydajności sklepu:</span><span class="sxs-lookup"><span data-stu-id="6b9f8-109">This report provides a snapshot of following summaries as part of store performance:</span></span>

- <span data-ttu-id="6b9f8-110">Podsumowanie sprzedaży brutto</span><span class="sxs-lookup"><span data-stu-id="6b9f8-110">Gross sales summary</span></span>
- <span data-ttu-id="6b9f8-111">Podsumowanie typów metod płatności</span><span class="sxs-lookup"><span data-stu-id="6b9f8-111">Tender type summary</span></span>
- <span data-ttu-id="6b9f8-112">Podsumowanie podatków</span><span class="sxs-lookup"><span data-stu-id="6b9f8-112">Tax summary</span></span>
- <span data-ttu-id="6b9f8-113">Podsumowanie zastępowania cen</span><span class="sxs-lookup"><span data-stu-id="6b9f8-113">Price overrides summary</span></span>
- <span data-ttu-id="6b9f8-114">Podsumowanie rabatów</span><span class="sxs-lookup"><span data-stu-id="6b9f8-114">Discounts summary</span></span>
