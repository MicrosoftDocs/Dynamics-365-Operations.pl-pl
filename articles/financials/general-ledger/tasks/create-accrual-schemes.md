---
title: Tworzenie schematów naliczania
description: Ten przewodnik po zadaniach prowadzi przez proces tworzenia schematu naliczania.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "355295"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="e558f-103">Tworzenie schematów naliczania</span><span class="sxs-lookup"><span data-stu-id="e558f-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e558f-104">Ten przewodnik po zadaniach prowadzi przez proces tworzenia schematu naliczania.</span><span class="sxs-lookup"><span data-stu-id="e558f-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="e558f-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="e558f-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="e558f-106">Wybierz kolejno opcje Księga główna > Konfiguracja arkusza > Schematy naliczania.</span><span class="sxs-lookup"><span data-stu-id="e558f-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="e558f-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e558f-107">Click New.</span></span>
3. <span data-ttu-id="e558f-108">W polu Identyfikacja naliczania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e558f-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="e558f-109">W polu Opis schematu naliczania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e558f-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="e558f-110">W polu Debet podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="e558f-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="e558f-111">Zdefiniowane konto główne zastąpi konto główne strony debetowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="e558f-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="e558f-112">W polu Kredyt podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="e558f-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="e558f-113">Zdefiniowane konto główne zastąpi konto główne strony kredytowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="e558f-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="e558f-114">W polu Załącznik wybierz sposób dobierania załącznika podczas księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="e558f-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="e558f-115">W polu Opis wpisz wartość opisującą transakcje, które będą księgowane.</span><span class="sxs-lookup"><span data-stu-id="e558f-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="e558f-116">W polu Częstotliwość okresu wybierz, jak często mają mieć miejsce transakcje.</span><span class="sxs-lookup"><span data-stu-id="e558f-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="e558f-117">W polu Liczba wystąpień według okresu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="e558f-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="e558f-118">W polu Księguj transakcje wybierz, kiedy transakcje mają być księgowane, np. Miesięcznie.</span><span class="sxs-lookup"><span data-stu-id="e558f-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

