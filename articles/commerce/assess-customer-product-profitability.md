---
title: Ocenianie rentowności odbiorców i produktów
description: W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych Dynamics 365 Commerce.
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
ms.openlocfilehash: 3218a29995791ce0d9a42d5b6d898d6e548f0f1d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023629"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="32646-103">Ocenianie rentowności odbiorców i produktów</span><span class="sxs-lookup"><span data-stu-id="32646-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="32646-104">W tym artykule wyjaśniono, jak za pomocą funkcji analizy w pamięci i w czasie rzeczywistym uzyskać dostęp, eksplorować i wyciągać wnioski o rentowności odbiorców i produktów z danych Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="32646-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="32646-105">W Commerce użytkownicy mogą analizować rentowność dla najlepszych odbiorców (10-100) na różnych poziomach hierarchii organizacji, na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="32646-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="32646-106">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="32646-106">Sales amount</span></span>
- <span data-ttu-id="32646-107">Ilość</span><span class="sxs-lookup"><span data-stu-id="32646-107">Quantity</span></span>
- <span data-ttu-id="32646-108">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="32646-108">Gross profit margin</span></span>
- <span data-ttu-id="32646-109">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="32646-109">Margin percentage</span></span>

<span data-ttu-id="32646-110">Na potrzeby tej analizy można używać gotowych raportów **Najlepsi sprzedaży**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="32646-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="32646-111">Obszar roboczy **Zarządzanie sklepem** &gt; **Retail i Commerce** &gt; **Kanały** &gt; **Zarządzanie sklepem** &gt; **Raporty** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="32646-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="32646-112">Sekcja **Zapytania i raporty** &gt; **Retail i Commerce** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych odbiorców**</span><span class="sxs-lookup"><span data-stu-id="32646-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="32646-113">W ten sam sposób użytkownicy mogą analizować rentowność dla najlepszych produktów (10-100) na różnych poziomach hierarchii organizacji, na podstawie następujących kryteriów:</span><span class="sxs-lookup"><span data-stu-id="32646-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="32646-114">Kwota sprzedaży</span><span class="sxs-lookup"><span data-stu-id="32646-114">Sales amount</span></span>
- <span data-ttu-id="32646-115">Ilość</span><span class="sxs-lookup"><span data-stu-id="32646-115">Quantity</span></span>
- <span data-ttu-id="32646-116">Marża zysku brutto</span><span class="sxs-lookup"><span data-stu-id="32646-116">Gross profit margin</span></span>
- <span data-ttu-id="32646-117">Wartość procentowa marży</span><span class="sxs-lookup"><span data-stu-id="32646-117">Margin percentage</span></span>

<span data-ttu-id="32646-118">Na potrzeby tej analizy można używać gotowych raportów **Najlepsze produkty**, które można otworzyć z następujących lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="32646-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="32646-119">Obszar roboczy **Zarządzanie sklepem** &gt; **Retail i Commerce** &gt; **Kanały** &gt; **Zarządzanie sklepem** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="32646-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="32646-120">Obszar roboczy **Zarządzanie kategoriami i produktami** &gt; **Retail i Commerce** &gt; **Produkty i kategorie** &gt; **Zarządzanie sklepem** &gt; **Raporty** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="32646-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="32646-121">Sekcja **Zapytania i raporty** &gt; **Retail i Commerce** &gt; **Zapytania i raporty** &gt; **Raporty ze sprzedaży** &gt; **Raport najlepszych produktów**</span><span class="sxs-lookup"><span data-stu-id="32646-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
