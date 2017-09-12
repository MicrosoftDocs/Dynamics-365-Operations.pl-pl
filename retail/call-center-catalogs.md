---
title: "Katalogi biura obsługi"
description: "W tym artykule opisano funkcje katalogów specyficzne dla biur obsługi dostępne w programie Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7be87496ceaea2d1d5f97a5cc17e50dcddbaf33d
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="call-center-catalogs"></a><span data-ttu-id="6869f-103">Katalogi biura obsługi</span><span class="sxs-lookup"><span data-stu-id="6869f-103">Call center catalogs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="6869f-104">W tym artykule opisano funkcje katalogów specyficzne dla biur obsługi dostępne w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="6869f-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="6869f-105">W biurze obsługi można używać katalogów produktów do identyfikowania produktów, które chcesz oferować odbiorcom.</span><span class="sxs-lookup"><span data-stu-id="6869f-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="6869f-106">Zazwyczaj biura obsługi korzystają z katalogów drukowanych.</span><span class="sxs-lookup"><span data-stu-id="6869f-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="6869f-107">Projektowanie i druk katalogów odbywa się poza programem Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="6869f-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="6869f-108">Możesz jednak utworzyć i zapisać formularz cyfrowy w postaci katalogu za pomocą tych samych stron, których używasz do konfiguracji katalogów sieci sprzedaży online.</span><span class="sxs-lookup"><span data-stu-id="6869f-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="6869f-109">Przed stworzeniem katalogu należy skonfigurować asortymenty produktów oraz przypisać asortymenty do biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="6869f-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="6869f-110">Następnie należy dodać produkty do katalogu, zaznaczając produkty z tych asortymentów.</span><span class="sxs-lookup"><span data-stu-id="6869f-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="6869f-111">Po dodaniu produktów do katalogu i zakończeniu pracy z katalogiem, należy sprawdzić poprawność katalogu, aby sprawdzić dane.</span><span class="sxs-lookup"><span data-stu-id="6869f-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="6869f-112">Następnie należy przesłać katalog do przejrzenia i zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="6869f-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="6869f-113">Po zatwierdzeniu katalogu może on zostać opublikowany.</span><span class="sxs-lookup"><span data-stu-id="6869f-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="6869f-114">Po utworzeniu katalogu dla biura obsługi, można wykonać migawkę danych katalogu w momencie opublikowania katalogu.</span><span class="sxs-lookup"><span data-stu-id="6869f-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="6869f-115">Ta funkcja migawki umożliwia uzyskanie dostępu do określonej wersji katalogu, nawet jeśli ulegnie ona później zmianie i aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="6869f-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="6869f-116">Katalogi biura obsługi można również ustawić w taki sposób, aby uwzględnić także następujące funkcje opcjonalne:</span><span class="sxs-lookup"><span data-stu-id="6869f-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="6869f-117">**Kody źródłowe** — kody, które są używane do śledzenia odpowiedzi odbiorcy na określone katalogi.</span><span class="sxs-lookup"><span data-stu-id="6869f-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="6869f-118">**Produkty bezpłatne** — produkty, które są uwzględniane w zamówieniu odbiorcy bez dodatkowych opłat.</span><span class="sxs-lookup"><span data-stu-id="6869f-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="6869f-119">Produkty te są dodawane do zamówienia automatycznie po wprowadzeniu do zamówienia kodu źródłowego dla katalogu.</span><span class="sxs-lookup"><span data-stu-id="6869f-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="6869f-120">**Skrypty** — teksty, które pracownik biura obsługi odczytuje w rozmowie z odbiorcą podczas tworzenia zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6869f-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="6869f-121">Skrypty mogą obejmować powitania lub sugestie dotyczące zakupu.</span><span class="sxs-lookup"><span data-stu-id="6869f-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="6869f-122">**Układ strony** — określa położenie produktów na stronie w wydrukowanym katalogu.</span><span class="sxs-lookup"><span data-stu-id="6869f-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="6869f-123">Te informacje są używane dla raportu z analizy obszaru katalogu.</span><span class="sxs-lookup"><span data-stu-id="6869f-123">This information is used for the catalog area analysis report.</span></span>





