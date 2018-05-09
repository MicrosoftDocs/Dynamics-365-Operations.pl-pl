---
title: "Analizowanie trendów i wzorców sprzedaży"
description: "W module Microsoft Dynamics 365 for Retail istnieje możliwość badania trendów i wzorców sprzedaży w czasie rzeczywistym."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailChannelReport, SysOperationTemplateForm, SysReportViewerForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: aff865f3db64246a963f4ae598c64495cc6d7a88
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="analyze-sales-trends-and-patterns"></a><span data-ttu-id="ad7b6-103">Analizowanie trendów i wzorców sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ad7b6-103">Analyze sales trends and patterns</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ad7b6-104">W module Microsoft Dynamics 365 for Retail istnieje możliwość badania trendów i wzorców sprzedaży w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="ad7b6-104">You can study sales trends and patterns in real time in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="ad7b6-105">W programie Dynamics 365 for Retail użytkownicy mogą badać trendy i wzorce sprzedaży w czasie rzeczywistym na różnych poziomach hierarchii organizacyjnej w okresie wielu lat, wykorzystując do tego gotowy raport **Raport sprzedaży w kanale wg lat**.</span><span class="sxs-lookup"><span data-stu-id="ad7b6-105">As part of Dynamics 365 for Retail, users can study sales trends and patterns in real time across different levels of the organization hierarchy over a period of years by using the out-of-box **Channel sales by year** report.</span></span> <span data-ttu-id="ad7b6-106">Raport można otworzyć z dowolnej z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="ad7b6-106">You can open this report from any of the following locations:</span></span>

-   <span data-ttu-id="ad7b6-107">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport sprzedaży w kanale wg lat**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-107">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
-   <span data-ttu-id="ad7b6-108">Obszar roboczy **Finanse sklepu sieciowego** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Finanse sklepu sieciowego** &gt; **Raporty** &gt; **Raport sprzedaży w kanale wg lat**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-108">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
-   <span data-ttu-id="ad7b6-109">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport sprzedaży w kanale wg lat**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-109">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by year report**</span></span>

<span data-ttu-id="ad7b6-110">Użytkownicy mogą również badać trendy i wzorce sprzedaży w ujęciu godzinowym na różnych poziomach hierarchii organizacyjnej w wybranym okresie, wykorzystując do tego gotowy raport **Raport sprzedaży w kanale wg godzin**.</span><span class="sxs-lookup"><span data-stu-id="ad7b6-110">Users can also study sales trends and patterns by hour across different levels of the organization hierarchy over a selected period by using the out-of-box **Channel sales by hour** report.</span></span> <span data-ttu-id="ad7b6-111">Raport można otworzyć z dowolnej z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="ad7b6-111">You can open this report from any of the following locations:</span></span>

-   <span data-ttu-id="ad7b6-112">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport sprzedaży w kanale wg godzin**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-112">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
-   <span data-ttu-id="ad7b6-113">Obszar roboczy **Finanse sklepu sieciowego** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Finanse sklepu sieciowego** &gt; **Raporty** &gt; **Raport sprzedaży w kanale wg godzin**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-113">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
-   <span data-ttu-id="ad7b6-114">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport sprzedaży w kanale wg godzin**</span><span class="sxs-lookup"><span data-stu-id="ad7b6-114">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by hour report**</span></span>



