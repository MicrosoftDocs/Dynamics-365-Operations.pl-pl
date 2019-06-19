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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec36ead402882c1022811b7b398a03c6325ef7c0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556626"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="f4a11-103">EUR-00015 Szukanie strony za pomocą identyfikatora VAT</span><span class="sxs-lookup"><span data-stu-id="f4a11-103">EUR-00015 Party search using VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4a11-104">Ta procedura pokazuje, jak przeprowadzić wyszukiwanie partii przy użyciu identyfikatora rejestracji.</span><span class="sxs-lookup"><span data-stu-id="f4a11-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="f4a11-105">Zanim będzie można wykonać tę procedurę, należy skonfigurować identyfikatory VAT oraz wprowadzić wszelkie identyfikatory VAT dla dostawców, odbiorców i firm.</span><span class="sxs-lookup"><span data-stu-id="f4a11-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="f4a11-106">Ta procedura dotyczy wszystkich krajów/regionów Europy.</span><span class="sxs-lookup"><span data-stu-id="f4a11-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="f4a11-107">Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF, której podstawowy adres mieści się w Niemczech.</span><span class="sxs-lookup"><span data-stu-id="f4a11-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="f4a11-108">Procedura jest przeznaczona dla kierowników odpowiedzialnych za rozliczenia z dostawcami i odbiorcami.</span><span class="sxs-lookup"><span data-stu-id="f4a11-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="f4a11-109">Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="f4a11-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="f4a11-110">Wybierz kolejno opcje Administrowanie organizacją > Globalna książka adresowa > Globalna książka adresowa.</span><span class="sxs-lookup"><span data-stu-id="f4a11-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="f4a11-111">Kliknij opcję Wyszukiwanie identyfikatorów rejestracji.</span><span class="sxs-lookup"><span data-stu-id="f4a11-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="f4a11-112">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="f4a11-112">Click Add.</span></span>
4. <span data-ttu-id="f4a11-113">W polu Typ rejestracji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4a11-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="f4a11-114">Na przykład jeśli chcesz znaleźć strony z identyfikatorem rejestracji o typie Identyfikator VAT, zaznacz opcję Identyfikator VAT.</span><span class="sxs-lookup"><span data-stu-id="f4a11-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="f4a11-115">W polu kraj/region wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4a11-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="f4a11-116">Na przykład wpisz DEU.</span><span class="sxs-lookup"><span data-stu-id="f4a11-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="f4a11-117">W polu Numer rejestracji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="f4a11-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="f4a11-118">Kliknij przycisk Znajdź.</span><span class="sxs-lookup"><span data-stu-id="f4a11-118">Click Find.</span></span>
    * <span data-ttu-id="f4a11-119">Zostaną wyświetlone wszystkie strony o takim identyfikatorze rejestracji.</span><span class="sxs-lookup"><span data-stu-id="f4a11-119">All parties with that registration ID will be displayed.</span></span>  

