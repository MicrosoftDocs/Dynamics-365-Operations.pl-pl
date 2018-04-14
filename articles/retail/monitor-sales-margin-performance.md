---
title: "Monitorowanie wydajności sprzedaży i marży"
description: "W programie Microsoft Dynamics 365 for Retail istnieje możliwość monitorowania wyników sprzedaży i osiąganych marż w czasie rzeczywistym."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4b90d7a9290fb7485fffe959057516795226d99b
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="89ccd-103">Monitorowanie wydajności sprzedaży i marży</span><span class="sxs-lookup"><span data-stu-id="89ccd-103">Monitor sales and margin performance</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="89ccd-104">W programie Microsoft Dynamics 365 for Retail istnieje możliwość monitorowania wyników sprzedaży i osiąganych marż w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="89ccd-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="89ccd-105">W programie Dynamics 365 for Retail użytkownicy mogą monitorować wyniki sprzedaży i uzyskiwane marże w czasie rzeczywistym na różnych poziomach hierarchii organizacyjnej dla następujących wymiarów:</span><span class="sxs-lookup"><span data-stu-id="89ccd-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

-   <span data-ttu-id="89ccd-106">Produkty</span><span class="sxs-lookup"><span data-stu-id="89ccd-106">Products</span></span>
-   <span data-ttu-id="89ccd-107">Kategorie</span><span class="sxs-lookup"><span data-stu-id="89ccd-107">Categories</span></span>
-   <span data-ttu-id="89ccd-108">Rabaty</span><span class="sxs-lookup"><span data-stu-id="89ccd-108">Discounts</span></span>
-   <span data-ttu-id="89ccd-109">Lata jako przedział czasu</span><span class="sxs-lookup"><span data-stu-id="89ccd-109">Years as time period</span></span>
-   <span data-ttu-id="89ccd-110">Kasy/terminale</span><span class="sxs-lookup"><span data-stu-id="89ccd-110">Registers/terminals</span></span>
-   <span data-ttu-id="89ccd-111">Personel/pracownicy</span><span class="sxs-lookup"><span data-stu-id="89ccd-111">Staff/employees</span></span>
-   <span data-ttu-id="89ccd-112">Odbiorcy</span><span class="sxs-lookup"><span data-stu-id="89ccd-112">Customers</span></span>
-   <span data-ttu-id="89ccd-113">Jednostki operacyjne</span><span class="sxs-lookup"><span data-stu-id="89ccd-113">Operating units</span></span>

<span data-ttu-id="89ccd-114">Ponadto dwa specjalne raporty wykorzystujące funkcję struktury hierarchicznej pozwalają użytkownikom monitorować osiąganą sprzedaż i marże poprzez przechodzenie do szczegółów z najwyższego węzła kategorii do węzłów poszczególnych liści kategorii w domyślnej hierarchii kategorii produktów detalicznych.</span><span class="sxs-lookup"><span data-stu-id="89ccd-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="89ccd-115">Użytkownicy mogą również przechodzić do szczegółów z najwyższej jednostki operacyjnej do poszczególnych kanałów w hierarchii organizacyjnej, którą zdefiniowano jako domyślną hierarchię organizacyjną dla hierarchii raportowania sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="89ccd-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="89ccd-116">Raporty można otwierać z dowolnej z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="89ccd-116">You can open the reports from any of the following locations:</span></span>

-   <span data-ttu-id="89ccd-117">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="89ccd-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="89ccd-118">Obszar roboczy **Zarządzanie kategoriami i produktami** &gt; **Handel detaliczny** &gt; **Produkty i kategorie** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="89ccd-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="89ccd-119">Obszar roboczy **Zarządzanie cenami i rabatami** &gt; **Handel detaliczny** &gt; **Ceny i rabaty** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="89ccd-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="89ccd-120">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="89ccd-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>



