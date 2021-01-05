---
title: EUR-00015 Szukanie strony za pomocą identyfikatora VAT
description: Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 401971b6f146f1df028291ba0f691ccac5f1966d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408348"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="b0b83-103">EUR-00015 Szukanie strony za pomocą identyfikatora VAT</span><span class="sxs-lookup"><span data-stu-id="b0b83-103">EUR-00015 Party search using VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b0b83-104">Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji.</span><span class="sxs-lookup"><span data-stu-id="b0b83-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="b0b83-105">Zanim będzie można wykonać tę procedurę, należy skonfigurować identyfikatory VAT oraz wprowadzić wszelkie identyfikatory VAT dla dostawców, odbiorców i firm.</span><span class="sxs-lookup"><span data-stu-id="b0b83-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="b0b83-106">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="b0b83-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="b0b83-107">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="b0b83-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="b0b83-108">Procedura jest przeznaczona dla kierowników odpowiedzialnych za rozliczenia z dostawcami i odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="b0b83-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="b0b83-109">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="b0b83-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="b0b83-110">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Globalna książka adresowa.</span><span class="sxs-lookup"><span data-stu-id="b0b83-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="b0b83-111">Kliknij opcję Wyszukiwanie identyfikatorów rejestracji.</span><span class="sxs-lookup"><span data-stu-id="b0b83-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="b0b83-112">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="b0b83-112">Click Add.</span></span>
4. <span data-ttu-id="b0b83-113">W polu Typ rejestracji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b0b83-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="b0b83-114">Na przykład jeśli chcesz znaleźć strony z identyfikatorem rejestracji o typie Identyfikator VAT, zaznacz opcję Identyfikator VAT.</span><span class="sxs-lookup"><span data-stu-id="b0b83-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="b0b83-115">W polu kraj/region wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="b0b83-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="b0b83-116">Na przykład wpisz DEU.</span><span class="sxs-lookup"><span data-stu-id="b0b83-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="b0b83-117">W polu Numer rejestracji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="b0b83-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="b0b83-118">Kliknij przycisk Znajdź.</span><span class="sxs-lookup"><span data-stu-id="b0b83-118">Click Find.</span></span>
    * <span data-ttu-id="b0b83-119">Zostaną wyświetlone wszystkie strony o takim identyfikatorze rejestracji.</span><span class="sxs-lookup"><span data-stu-id="b0b83-119">All parties with that registration ID will be displayed.</span></span>  

