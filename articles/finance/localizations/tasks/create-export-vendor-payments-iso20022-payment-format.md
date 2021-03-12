---
title: Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022
description: W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1df738e3925dc23e7723d93f33acf6a9d811b113
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964548"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="d3dbc-103">Tworzenie i eksportowanie płatności dla dostawcy przy użyciu formatu płatności ISO20022</span><span class="sxs-lookup"><span data-stu-id="d3dbc-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d3dbc-104">W tym temacie pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="d3dbc-105">Jest to piąta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="d3dbc-106">W tym przykładzie użyj danych demonstracyjnych DEMF.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="d3dbc-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="d3dbc-107">Example</span></span>

1.    <span data-ttu-id="d3dbc-108">Wybierz kolejno opcje **Rozrachunki z dostawcami > Płatności > Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.    <span data-ttu-id="d3dbc-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-109">Click **New**.</span></span>
3.    <span data-ttu-id="d3dbc-110">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-110">In the **Name** field, enter or select a value.</span></span>
4.    <span data-ttu-id="d3dbc-111">Kliknij kolejno pozycje **Wiersze > Propozycja płatności -> Utwórz propozycję płatności**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.    <span data-ttu-id="d3dbc-112">Rozwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-112">Expand the **Records to include** section.</span></span>
6.    <span data-ttu-id="d3dbc-113">Kliknij przycisk **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-113">Click **Filter**.</span></span>
7.    <span data-ttu-id="d3dbc-114">Na liście zaznacz wiersz dla **tabeli Dostawcy** i **pola Konto dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.    <span data-ttu-id="d3dbc-115">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="d3dbc-116">Można stosować dowolne kryteria w celu wybrania transakcji z dostawcą, które mają zostać opłacone. W tym przykładzie zostanie użyte kryterium DE-001 jako konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12.    <span data-ttu-id="d3dbc-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-117">Click **OK**.</span></span>
13.    <span data-ttu-id="d3dbc-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-118">Click **OK**.</span></span>
14.    <span data-ttu-id="d3dbc-119">Kliknij opcję **Utwórz płatności**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="d3dbc-120">Generowanie pliku płatności ISO20022.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-120">Generate an ISO20022 payment file.</span></span>
    1.    <span data-ttu-id="d3dbc-121">Kliknij opcję **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-121">Click **Generate payments**.</span></span>
    2.    <span data-ttu-id="d3dbc-122">W polu **Metoda płatności** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.    <span data-ttu-id="d3dbc-123">W polu **Nazwa pliku** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="d3dbc-124">Na przykład z powodu płatności EUR wygenerowany plik będzie zgodny z SEPA.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="d3dbc-125">Polecenie przelewu ISO20022 i inne formaty płatności dostawców mogą też służyć do generowania płatności w innych walutach.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.    <span data-ttu-id="d3dbc-126">W polu **Konto bankowe** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3dbc-126">In the **Bank account** field, enter or select a value.</span></span>

