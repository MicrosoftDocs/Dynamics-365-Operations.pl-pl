---
title: Raporty cen detalicznych
description: Ten temat zawiera omówienie funkcji raportu cen, która pozwala na wyświetlanie nadchodzące zmian cen dla produktów w asortymencie.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: f317b22f2794dc71093068a51c8e9d4e6d7d55ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231159"
---
# <a name="retail-price-reports"></a><span data-ttu-id="073ba-103">Raporty cen detalicznych</span><span class="sxs-lookup"><span data-stu-id="073ba-103">Retail price reports</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="073ba-104">W celu zapewnienia konkurencyjnych cen klientom, sprzedawcy detaliczni często zmieniają ceny produktów.</span><span class="sxs-lookup"><span data-stu-id="073ba-104">In order to provide competitive prices to their customers, retailers often change prices of products.</span></span> <span data-ttu-id="073ba-105">Kierownicy sklepów mają możliwość łatwego dostępu do ostatnich i nadchodzących zmian cen, co pozwala im odpowiednio planować zasoby wymagane do aktualizacji etykiet z cenami na sklepowych półkach.</span><span class="sxs-lookup"><span data-stu-id="073ba-105">Store managers want the ability to easily access recent or upcoming price changes so that they can plan for the required resources to update the price labels displayed on the store shelves.</span></span> <span data-ttu-id="073ba-106">W wersji 10.0 programu Commerce kierownik sklepu może otworzyć raport **Cena**, przechodząc do menu **Wszystkie sklepy \> Sklep \> Raport cen** i wyświetlając zaktualizowane ceny produktów skojarzone ze sklepem.</span><span class="sxs-lookup"><span data-stu-id="073ba-106">With release 10.0 of Retail, a store manager can open the **Price** report by navigating to **All stores \> Store \> Price report** and viewing the updated prices for the products associated to the store.</span></span> 

<span data-ttu-id="073ba-107">Aby włączyć raport cen, parametr **Włącz raport cen w sklepie** musi być włączony.</span><span class="sxs-lookup"><span data-stu-id="073ba-107">To enable the price report, the **Enable price report for store** parameter must be turned on.</span></span> <span data-ttu-id="073ba-108">Ten parametr jest umieszczony na karcie **Parametry sprzedaży \> Rabaty \> Różne**. Otwarcie karty **Raport cen** wyświetla okno dialogowe z różnymi konfiguracjami.</span><span class="sxs-lookup"><span data-stu-id="073ba-108">This parameter is located on the **Commerce parameters \> Discounts \> Miscellaneous** tab. Opening the **Price report** page displays a dialog box with various configurations.</span></span> <span data-ttu-id="073ba-109">Poniżej przedstawiono listę dostępnych konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="073ba-109">The available configurations are listed below.</span></span>

| <span data-ttu-id="073ba-110">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="073ba-110">Configuration</span></span> | <span data-ttu-id="073ba-111">opis</span><span class="sxs-lookup"><span data-stu-id="073ba-111">Description</span></span> |
|---|---|
| <span data-ttu-id="073ba-112">Data Od / Data Do</span><span class="sxs-lookup"><span data-stu-id="073ba-112">From date / To date</span></span>| <span data-ttu-id="073ba-113">Zakres dat, dla których należy generować raport cen.</span><span class="sxs-lookup"><span data-stu-id="073ba-113">The date range for which the price report should be generated.</span></span> <span data-ttu-id="073ba-114">Czas trwania jest obecnie ograniczony do 7 dni.</span><span class="sxs-lookup"><span data-stu-id="073ba-114">The duration is currently limited to 7 days.</span></span> |
| <span data-ttu-id="073ba-115">Kanał</span><span class="sxs-lookup"><span data-stu-id="073ba-115">Channel</span></span>| <span data-ttu-id="073ba-116">Sklep, dla którego należy generować raport cen.</span><span class="sxs-lookup"><span data-stu-id="073ba-116">The store for which the price report should be generated.</span></span> |
| <span data-ttu-id="073ba-117">Wyświetl produkty z dostępnymi zapasami</span><span class="sxs-lookup"><span data-stu-id="073ba-117">Display products with available inventory</span></span>| <span data-ttu-id="073ba-118">Ustawienie **Tak** spowoduje wyświetlenie cen tylko dla tych produktów, które obecnie mają dostępne zapasy fizyczne w sklepie.</span><span class="sxs-lookup"><span data-stu-id="073ba-118">Setting this to **Yes** will show the prices for only those products which currently have physical inventory available in the store.</span></span> |
| <span data-ttu-id="073ba-119">Wyświetl ceny wariantów</span><span class="sxs-lookup"><span data-stu-id="073ba-119">Display prices for variants</span></span> | <span data-ttu-id="073ba-120">Ustawienie **Tak** spowoduje wyświetlenie cen wariantów wraz z produktami głównymi.</span><span class="sxs-lookup"><span data-stu-id="073ba-120">Setting this to **Yes** will display the prices of the variants along with the product masters.</span></span> <span data-ttu-id="073ba-121">Należy **włączyć** tę opcję tylko wówczas, gdy występują różne ceny wariantów, ponieważ liczba wierszy bardzo rośnie.</span><span class="sxs-lookup"><span data-stu-id="073ba-121">This should only be turned **On** if you have variant-specific prices, because the number of rows grows very large.</span></span> <span data-ttu-id="073ba-122">W przyszłych wersjach włączymy obsługę cen na podstawie wymiarów, tak aby kierownik sklepu mógł wybrać wymiary, dla których mają być wyświetlane ceny.</span><span class="sxs-lookup"><span data-stu-id="073ba-122">In future releases, we will enable the dimensions-based prices so that the store manager can choose the dimensions for which the prices should be displayed.</span></span> |
| <span data-ttu-id="073ba-123">Wyświetl produkty ze zmianami cen</span><span class="sxs-lookup"><span data-stu-id="073ba-123">Display products with price changes</span></span> | <span data-ttu-id="073ba-124">Ustawienie **Tak** spowoduje wyświetlanie cen tylko dla tych dat, w których cena została zmieniona.</span><span class="sxs-lookup"><span data-stu-id="073ba-124">Setting this to **Yes** will display the prices for only those dates on which the price has been changed.</span></span> <span data-ttu-id="073ba-125">Cena dla *jednego dnia przed* wybraną **Datą Od** zawsze będzie wyświetlana, tak aby kierownik sklepu mógł łatwo zidentyfikować produkty, których ceny nie zmieniły się przez cały wybrany okres, i mógł również łatwo wyświetlić bieżącą cenę.</span><span class="sxs-lookup"><span data-stu-id="073ba-125">The price for *one day before* the selected **From date** will always be displayed, so that the store manager can easily identity the products which have not changed prices for the entire selected duration, and can also view the current price.</span></span> |

<span data-ttu-id="073ba-126">Po wygenerowaniu raportu można pobrać plik programu Excel dla wszelkich dodatkowych potrzeb filtrowania.</span><span class="sxs-lookup"><span data-stu-id="073ba-126">After the report is generated, the Excel file can be downloaded for any additional filtering needs.</span></span> <span data-ttu-id="073ba-127">Raport cen może również służyć do sprawdzania historycznych cen produktów dla dat z przeszłości.</span><span class="sxs-lookup"><span data-stu-id="073ba-127">The price report can also be used to check the historical prices of products for past dates.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]