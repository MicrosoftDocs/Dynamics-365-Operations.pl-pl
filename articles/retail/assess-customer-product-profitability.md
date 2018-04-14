---
title: "Ocenianie rentowności odbiorców i produktów"
description: "W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych programu Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c603c065d57f08772c3b25cab8437cb7848e5fcb
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="3b414-103">Ocenianie rentowności odbiorców i produktów</span><span class="sxs-lookup"><span data-stu-id="3b414-103">Assess customer and product profitability</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="3b414-104">W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych programu Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="3b414-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="3b414-105">W programie Dynamics 365 for Retail użytkownicy mogą analizować rentowność dla najlepszych odbiorców (10-100) na różnych poziomach hierarchii organizacyjnej na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="3b414-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="3b414-106">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3b414-106">Sales amount</span></span>
-   <span data-ttu-id="3b414-107">Ilość</span><span class="sxs-lookup"><span data-stu-id="3b414-107">Quantity</span></span>
-   <span data-ttu-id="3b414-108">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="3b414-108">Gross profit margin</span></span>
-   <span data-ttu-id="3b414-109">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="3b414-109">Margin percentage</span></span>

<span data-ttu-id="3b414-110">Na potrzeby tej analizy można używać gotowych raportów **Najlepsi sprzedaży**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="3b414-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="3b414-111">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="3b414-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
-   <span data-ttu-id="3b414-112">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="3b414-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="3b414-113">W ten sam sposób użytkownicy mogą analizować rentowność dla najlepszych produktów (10-100) na różnych poziomach hierarchii organizacji, na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="3b414-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

-   <span data-ttu-id="3b414-114">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3b414-114">Sales amount</span></span>
-   <span data-ttu-id="3b414-115">Ilość</span><span class="sxs-lookup"><span data-stu-id="3b414-115">Quantity</span></span>
-   <span data-ttu-id="3b414-116">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="3b414-116">Gross profit margin</span></span>
-   <span data-ttu-id="3b414-117">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="3b414-117">Margin percentage</span></span>

<span data-ttu-id="3b414-118">Na potrzeby tej analizy można używać gotowych raportów **Najlepsze produkty**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="3b414-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

-   <span data-ttu-id="3b414-119">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="3b414-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="3b414-120">Obszar roboczy **Zarządzanie kategoriami i produktami** &gt; **Handel detaliczny** &gt; **Produkty i kategorie** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="3b414-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
-   <span data-ttu-id="3b414-121">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="3b414-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>




