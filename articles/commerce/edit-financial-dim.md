---
title: Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej
description: W tym temacie opisano sposób edytowania wymiarów finansowych dla transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: e26bd4eb53fa44330f15c7cda004cb3d19dfec6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459751"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="66802-103">Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="66802-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66802-104">W tym temacie opisano sposób edytowania wymiarów finansowych dla transakcji sprzedaży detalicznej w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="66802-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="66802-105">Edytowanie wymiarów finansowych</span><span class="sxs-lookup"><span data-stu-id="66802-105">Edit financial dimensions</span></span>

<span data-ttu-id="66802-106">Aby edytować wymiary finansowe dla transakcji sprzedaży detalicznej w centrali Commerce, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="66802-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="66802-107">Otwórz stronę **Konfiguracja wymiarów finansowych dla aplikacji integrujących**.</span><span class="sxs-lookup"><span data-stu-id="66802-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="66802-108">Wybierz aktywny rekord **Integracja wymiarów domyślnych**.</span><span class="sxs-lookup"><span data-stu-id="66802-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="66802-109">Upewnij się, że na skróconej karcie **Wymiary finansowe** wszystkie wymiary, które chcesz edytować w arkuszu programu Excel, znajdują się na liście **Wybrane**.</span><span class="sxs-lookup"><span data-stu-id="66802-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="66802-110">Aby uzyskać więcej informacji, zobacz [Jednostki danych](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span><span class="sxs-lookup"><span data-stu-id="66802-110">For more information, see [Data entities](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span></span>
1. <span data-ttu-id="66802-111">Pobierz i otwórz plik programu Excel ze strony **Zestawienia** lub **Transakcje sprzedaży detalicznej** albo kafelka **Weryfikacje transakcji zakończone niepowodzeniem** w obszarze roboczym **Finanse sklepu**.</span><span class="sxs-lookup"><span data-stu-id="66802-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="66802-112">Aby zmienić wymiar finansowy transakcji, wybierz pozycję **Projekt**, a następnie wybierz symbol ołówka obok wiersza **Transakcja (podlegająca inspekcji)**.</span><span class="sxs-lookup"><span data-stu-id="66802-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="66802-113">Znajdź i wybierz pole **FinancialDimensionDisplayValue**, zaznacz komórkę w części nagłówka arkusza programu Excel, a następnie wybierz pozycję **Dodaj etykietę**.</span><span class="sxs-lookup"><span data-stu-id="66802-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="66802-114">Zaznacz komórkę pod komórką wybraną w poprzednim kroku, wybierz opcję **Dodaj wartość**, a następnie wybierz opcję **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="66802-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="66802-115">Wymiary finansowe zostaną dodane do arkusza programu Excel, po czym będzie można je edytować i publikować.</span><span class="sxs-lookup"><span data-stu-id="66802-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="66802-116">Aby zmienić wymiary w wierszach transakcji, zaznacz wiersz **Transakcje sprzedaży (podlegające inspekcji)**, wybierz symbol ołówka, a następnie powtórz kroki 6 i 7.</span><span class="sxs-lookup"><span data-stu-id="66802-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="66802-117">Aby zmienić wymiary w wierszach płatności, zaznacz wiersz **Transakcje płatności (podlegające inspekcji)**, wybierz symbol ołówka, a następnie powtórz kroki 6 i 7.</span><span class="sxs-lookup"><span data-stu-id="66802-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66802-118">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="66802-118">Additional resources</span></span>

[<span data-ttu-id="66802-119">Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką</span><span class="sxs-lookup"><span data-stu-id="66802-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="66802-120">Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="66802-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="66802-121">Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="66802-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="66802-122">Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="66802-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
