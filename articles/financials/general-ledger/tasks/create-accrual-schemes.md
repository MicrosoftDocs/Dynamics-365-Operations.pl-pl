--- 
title: "Tworzenie schematów naliczania"
description: Ten przewodnik po zadaniach prowadzi przez proces tworzenia schematu naliczania.
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d1d7d531f547f517d1f39a6b181d9a7a782771e6
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="create-accrual-schemes"></a><span data-ttu-id="5b1af-103">Tworzenie schematów naliczania</span><span class="sxs-lookup"><span data-stu-id="5b1af-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5b1af-104">Ten przewodnik po zadaniach prowadzi przez proces tworzenia schematu naliczania.</span><span class="sxs-lookup"><span data-stu-id="5b1af-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="5b1af-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="5b1af-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5b1af-106">Wybierz kolejno opcje Księga główna > Konfiguracja arkusza > Schematy naliczania.</span><span class="sxs-lookup"><span data-stu-id="5b1af-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="5b1af-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="5b1af-107">Click New.</span></span>
3. <span data-ttu-id="5b1af-108">W polu Identyfikacja naliczania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5b1af-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="5b1af-109">W polu Opis schematu naliczania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="5b1af-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="5b1af-110">W polu Debet podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="5b1af-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="5b1af-111">Zdefiniowane konto główne zastąpi konto główne strony debetowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="5b1af-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="5b1af-112">W polu Kredyt podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="5b1af-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="5b1af-113">Zdefiniowane konto główne zastąpi konto główne strony kredytowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="5b1af-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="5b1af-114">W polu Załącznik wybierz sposób dobierania załącznika podczas księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="5b1af-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="5b1af-115">W polu Opis wpisz wartość opisującą transakcje, które będą księgowane.</span><span class="sxs-lookup"><span data-stu-id="5b1af-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="5b1af-116">W polu Częstotliwość okresu wybierz, jak często mają mieć miejsce transakcje.</span><span class="sxs-lookup"><span data-stu-id="5b1af-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="5b1af-117">W polu Liczba wystąpień według okresu wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="5b1af-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="5b1af-118">W polu Księguj transakcje wybierz, kiedy transakcje mają być księgowane, np. Miesięcznie.</span><span class="sxs-lookup"><span data-stu-id="5b1af-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>


