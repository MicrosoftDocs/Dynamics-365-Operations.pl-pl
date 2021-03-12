---
title: Monitorowanie wydajności sprzedaży i marży
description: Za pomocą Dynamics 365 Commerce istnieje możliwość monitorowania wyników sprzedaży i osiąganych marż w czasie rzeczywistym.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51dc7c4b62a497e3dc9279b3c5a616057316c106
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985893"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="9ac63-103">Monitorowanie wydajności sprzedaży i marży</span><span class="sxs-lookup"><span data-stu-id="9ac63-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9ac63-104">Za pomocą Dynamics 365 Commerce istnieje możliwość monitorowania wyników sprzedaży i osiąganych marż w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="9ac63-104">You can monitor sales and margin performance in real time using Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9ac63-105">W usłudze Commerce użytkownicy mogą monitorować wyniki sprzedaży i uzyskiwane marże w czasie rzeczywistym na różnych poziomach hierarchii organizacyjnej dla następujących wymiarów:</span><span class="sxs-lookup"><span data-stu-id="9ac63-105">As part of Commerce, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="9ac63-106">Produkty</span><span class="sxs-lookup"><span data-stu-id="9ac63-106">Products</span></span>
- <span data-ttu-id="9ac63-107">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9ac63-107">Categories</span></span>
- <span data-ttu-id="9ac63-108">Rabaty</span><span class="sxs-lookup"><span data-stu-id="9ac63-108">Discounts</span></span>
- <span data-ttu-id="9ac63-109">Lata jako przedział czasu</span><span class="sxs-lookup"><span data-stu-id="9ac63-109">Years as time period</span></span>
- <span data-ttu-id="9ac63-110">Kasy/terminale</span><span class="sxs-lookup"><span data-stu-id="9ac63-110">Registers/terminals</span></span>
- <span data-ttu-id="9ac63-111">Personel/pracownicy</span><span class="sxs-lookup"><span data-stu-id="9ac63-111">Staff/employees</span></span>
- <span data-ttu-id="9ac63-112">Odbiorcy</span><span class="sxs-lookup"><span data-stu-id="9ac63-112">Customers</span></span>
- <span data-ttu-id="9ac63-113">Jednostki operacyjne</span><span class="sxs-lookup"><span data-stu-id="9ac63-113">Operating units</span></span>

<span data-ttu-id="9ac63-114">Ponadto dwa specjalne raporty wykorzystujące funkcję struktury hierarchicznej pozwalają użytkownikom monitorować osiąganą sprzedaż i marże poprzez przechodzenie do szczegółów z najwyższego węzła kategorii do węzłów poszczególnych liści kategorii w domyślnej hierarchii kategorii produktów.</span><span class="sxs-lookup"><span data-stu-id="9ac63-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default product category hierarchy.</span></span> <span data-ttu-id="9ac63-115">Użytkownicy mogą również przechodzić do szczegółów z najwyższej jednostki operacyjnej do poszczególnych kanałów w hierarchii organizacyjnej, którą zdefiniowano jako domyślną hierarchię organizacyjną dla raportowania.</span><span class="sxs-lookup"><span data-stu-id="9ac63-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for reporting.</span></span> <span data-ttu-id="9ac63-116">Raporty można otwierać z dowolnej z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="9ac63-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="9ac63-117">Obszar roboczy **Zarządzanie sklepem** &gt; **Handel detaliczny i komercyjny** &gt; **Kanały** &gt; **Zarządzanie sklepem** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="9ac63-117">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="9ac63-118">Obszar roboczy **Zarządzanie kategoriami i produktami** &gt; **Handel detaliczny i komercyjny** &gt; **Produkty i kategorie** &gt; **Zarządzanie sklepem** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="9ac63-118">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Product and categories** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="9ac63-119">Obszar roboczy **Zarządzanie cenami i rabatami** &gt; **Handel detaliczny i komercyjny** &gt; **Ceny i rabaty** &gt; **Zarządzanie sklepem** &gt; **Raporty**</span><span class="sxs-lookup"><span data-stu-id="9ac63-119">**Pricing and discount management** workspace &gt; **Retail and Commerce** &gt; **Pricing and discounts** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="9ac63-120">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny i komercyjny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży**</span><span class="sxs-lookup"><span data-stu-id="9ac63-120">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>
