---
title: Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych
description: W tym temacie opisano sposób dodawania pól do skoroszytu programu Microsoft Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: dce5afdd440a3f953dea632183717d9d7273b032
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459752"
---
# <a name="add-fields-to-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="c1b47-103">Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="c1b47-103">Add fields to an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1b47-104">W tym temacie opisano sposób dodawania pól do skoroszytu programu Microsoft Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c1b47-104">This topic describes how to add fields to a Microsoft Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c1b47-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c1b47-105">Overview</span></span>

<span data-ttu-id="c1b47-106">Podczas generowania pliku programu Excel do edycji transakcji detalicznych plik zostaje wypełniony określonymi polami domyślnymi.</span><span class="sxs-lookup"><span data-stu-id="c1b47-106">When you generate an Excel file so that you can edit retail transactions, the file is filled with some default fields.</span></span> <span data-ttu-id="c1b47-107">Jeśli pole, które musi zostać zaktualizowane, nie jest domyślnie widoczne w wygenerowanym pliku programu Excel, można je dodać.</span><span class="sxs-lookup"><span data-stu-id="c1b47-107">If a field that must be updated isn't visible by default in the generated Excel file, you can add it.</span></span>

## <a name="add-fields-to-a-worksheet-in-an-excel-workbook"></a><span data-ttu-id="c1b47-108">Dodawanie pól do arkusza skoroszytu programu Excel</span><span class="sxs-lookup"><span data-stu-id="c1b47-108">Add fields to a worksheet in an Excel workbook</span></span>

<span data-ttu-id="c1b47-109">Aby dodać pola do skoroszyt programu Excel, by móc edytować transakcje sprzedaży detalicznej, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="c1b47-109">To add fields to an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="c1b47-110">Pobierz i otwórz plik programu Excel ze strony **Zestawienia** lub **Transakcje sprzedaży detalicznej** albo kafelka **Weryfikacje transakcji zakończone niepowodzeniem** w obszarze roboczym **Finanse sklepu**.</span><span class="sxs-lookup"><span data-stu-id="c1b47-110">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="c1b47-111">Wybierz **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c1b47-111">Select **Design**.</span></span>
1. <span data-ttu-id="c1b47-112">Zaznacz symbol ołówka dla żądanej tabeli, a następnie znajdź na liście dostępnych pól pole, które chcesz dodać, i wybierz je.</span><span class="sxs-lookup"><span data-stu-id="c1b47-112">Select the pencil symbol for the desired table, and then, in the list of available fields, find and select the field that you want to add.</span></span>
1. <span data-ttu-id="c1b47-113">Wybierz opcję **Dodaj**, a następnie opcję **Aktualizuj**.</span><span class="sxs-lookup"><span data-stu-id="c1b47-113">Select **Add**, and then select **Update**.</span></span> <span data-ttu-id="c1b47-114">Kolejność pól można zmieniać.</span><span class="sxs-lookup"><span data-stu-id="c1b47-114">You can reorder fields.</span></span>
1. <span data-ttu-id="c1b47-115">Po zakończeniu aktualizacji wybierz opcję **Odśwież**, aby pobrać dane dla nowej kolumny.</span><span class="sxs-lookup"><span data-stu-id="c1b47-115">After the update is completed, select **Refresh** to fetch the data for the new column.</span></span>

<span data-ttu-id="c1b47-116">Na tym etapie nowe pole oraz dane dla niego powinny być dostępne do edycji w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="c1b47-116">The new field and data for it should now be available for editing in Excel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1b47-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1b47-117">Additional resources</span></span>

[<span data-ttu-id="c1b47-118">Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką</span><span class="sxs-lookup"><span data-stu-id="c1b47-118">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="c1b47-119">Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy</span><span class="sxs-lookup"><span data-stu-id="c1b47-119">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="c1b47-120">Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej</span><span class="sxs-lookup"><span data-stu-id="c1b47-120">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="c1b47-121">Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych</span><span class="sxs-lookup"><span data-stu-id="c1b47-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)
