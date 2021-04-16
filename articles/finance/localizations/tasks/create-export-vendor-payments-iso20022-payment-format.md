---
title: Tworzenie i eksport płatności dla dostawcy przy użyciu formatu płatności ISO20022
description: W tej procedurze pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18c7d0b6c5c6a7f598f4b94f4dcf02df498d74cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822712"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="430e0-103">Tworzenie i eksportowanie płatności dla dostawcy przy użyciu formatu płatności ISO20022</span><span class="sxs-lookup"><span data-stu-id="430e0-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="430e0-104">W tym temacie pokazano sposób tworzenia wierszy w arkuszu płatności dostawcy oraz generowania pliku płatności dla dostawcy na przykładzie polecenia przelewu ISO2022.</span><span class="sxs-lookup"><span data-stu-id="430e0-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="430e0-105">Jest to piąta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="430e0-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="430e0-106">W tym przykładzie użyj danych demonstracyjnych DEMF.</span><span class="sxs-lookup"><span data-stu-id="430e0-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="430e0-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="430e0-107">Example</span></span>

1.    <span data-ttu-id="430e0-108">Wybierz kolejno opcje **Rozrachunki z dostawcami > Płatności > Arkusz płatności**.</span><span class="sxs-lookup"><span data-stu-id="430e0-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.    <span data-ttu-id="430e0-109">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="430e0-109">Click **New**.</span></span>
3.    <span data-ttu-id="430e0-110">W polu **Nazwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="430e0-110">In the **Name** field, enter or select a value.</span></span>
4.    <span data-ttu-id="430e0-111">Kliknij kolejno pozycje **Wiersze > Propozycja płatności -> Utwórz propozycję płatności**.</span><span class="sxs-lookup"><span data-stu-id="430e0-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.    <span data-ttu-id="430e0-112">Rozwiń sekcję **Rekordy do uwzględnienia**.</span><span class="sxs-lookup"><span data-stu-id="430e0-112">Expand the **Records to include** section.</span></span>
6.    <span data-ttu-id="430e0-113">Kliknij przycisk **Filtr**.</span><span class="sxs-lookup"><span data-stu-id="430e0-113">Click **Filter**.</span></span>
7.    <span data-ttu-id="430e0-114">Na liście zaznacz wiersz dla **tabeli Dostawcy** i **pola Konto dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="430e0-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.    <span data-ttu-id="430e0-115">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="430e0-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="430e0-116">Można stosować dowolne kryteria w celu wybrania transakcji z dostawcą, które mają zostać opłacone. W tym przykładzie zostanie użyte kryterium DE-001 jako konto dostawcy.</span><span class="sxs-lookup"><span data-stu-id="430e0-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12.    <span data-ttu-id="430e0-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="430e0-117">Click **OK**.</span></span>
13.    <span data-ttu-id="430e0-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="430e0-118">Click **OK**.</span></span>
14.    <span data-ttu-id="430e0-119">Kliknij opcję **Utwórz płatności**.</span><span class="sxs-lookup"><span data-stu-id="430e0-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="430e0-120">Generowanie pliku płatności ISO20022.</span><span class="sxs-lookup"><span data-stu-id="430e0-120">Generate an ISO20022 payment file.</span></span>
    1.    <span data-ttu-id="430e0-121">Kliknij opcję **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="430e0-121">Click **Generate payments**.</span></span>
    2.    <span data-ttu-id="430e0-122">W polu **Metoda płatności** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="430e0-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.    <span data-ttu-id="430e0-123">W polu **Nazwa pliku** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="430e0-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="430e0-124">Na przykład z powodu płatności EUR wygenerowany plik będzie zgodny z SEPA.</span><span class="sxs-lookup"><span data-stu-id="430e0-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="430e0-125">Polecenie przelewu ISO20022 i inne formaty płatności dostawców mogą też służyć do generowania płatności w innych walutach.</span><span class="sxs-lookup"><span data-stu-id="430e0-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.    <span data-ttu-id="430e0-126">W polu **Konto bankowe** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="430e0-126">In the **Bank account** field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]