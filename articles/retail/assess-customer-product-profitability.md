---
title: Ocenianie rentowności odbiorców i produktów
description: W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 28d4eeaa3fcae33f817690ad496b4b123a5838ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "326016"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="d2c77-103">Ocenianie rentowności odbiorców i produktów</span><span class="sxs-lookup"><span data-stu-id="d2c77-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d2c77-104">W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="d2c77-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span>

<span data-ttu-id="d2c77-105">W Dynamics 365 for Retail użytkownicy mogą analizować rentowność dla najlepszych odbiorców (10-100) na różnych poziomach hierarchii organizacji, na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="d2c77-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="d2c77-106">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d2c77-106">Sales amount</span></span>
- <span data-ttu-id="d2c77-107">Ilość</span><span class="sxs-lookup"><span data-stu-id="d2c77-107">Quantity</span></span>
- <span data-ttu-id="d2c77-108">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="d2c77-108">Gross profit margin</span></span>
- <span data-ttu-id="d2c77-109">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="d2c77-109">Margin percentage</span></span>

<span data-ttu-id="d2c77-110">Na potrzeby tej analizy można używać gotowych raportów **Najlepsi sprzedaży**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="d2c77-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="d2c77-111">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="d2c77-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="d2c77-112">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="d2c77-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="d2c77-113">W ten sam sposób użytkownicy mogą analizować rentowność dla najlepszych produktów (10-100) na różnych poziomach hierarchii organizacji, na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="d2c77-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="d2c77-114">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d2c77-114">Sales amount</span></span>
- <span data-ttu-id="d2c77-115">Ilość</span><span class="sxs-lookup"><span data-stu-id="d2c77-115">Quantity</span></span>
- <span data-ttu-id="d2c77-116">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="d2c77-116">Gross profit margin</span></span>
- <span data-ttu-id="d2c77-117">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="d2c77-117">Margin percentage</span></span>

<span data-ttu-id="d2c77-118">Na potrzeby tej analizy można używać gotowych raportów **Najlepsze produkty**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="d2c77-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="d2c77-119">Obszar roboczy **Zarządzanie sklepem sieciowym** &gt; **Handel detaliczny** &gt; **Kanały** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="d2c77-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="d2c77-120">Obszar roboczy **Zarządzanie kategoriami i produktami** &gt; **Handel detaliczny** &gt; **Produkty i kategorie** &gt; **Zarządzanie sklepem sieciowym** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="d2c77-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="d2c77-121">Sekcja **Zapytania i raporty** &gt; **Handel detaliczny** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="d2c77-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
