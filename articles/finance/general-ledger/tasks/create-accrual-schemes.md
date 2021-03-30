---
title: Tworzenie schematów naliczania
description: W tym temacie opisano sposób tworzenia schematu naliczania.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c021f71735e63c270e8f1998d77d4e4abcc5506
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236705"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="0ac4a-103">Tworzenie schematów naliczania</span><span class="sxs-lookup"><span data-stu-id="0ac4a-103">Create accrual schemes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ac4a-104">W tym temacie opisano sposób tworzenia schematu naliczania.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-104">This topic explains how to create an accrual scheme.</span></span> <span data-ttu-id="0ac4a-105">W zadaniu wykorzystano firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0ac4a-106">Otwórz **Okienko nawigacji > Moduły > Księga główna > Konfiguracja arkusza > Schematy naliczania**.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-106">Go to **Navigation pane > Modules > General ledger > Journal setup > Accrual schemes**.</span></span>
2. <span data-ttu-id="0ac4a-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-107">Select **New**.</span></span>
3. <span data-ttu-id="0ac4a-108">W polu **Identyfikacja naliczania** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-108">In the **Accrual identification** field, type a value.</span></span>
4. <span data-ttu-id="0ac4a-109">W polu **Opis schematu naliczania** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-109">In the **Description of accrual scheme** field, type a value.</span></span>
5. <span data-ttu-id="0ac4a-110">W polu **Debet** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-110">In the **Debit** field, specify the desired values.</span></span> <span data-ttu-id="0ac4a-111">Zdefiniowane konto główne zastąpi konto główne strony debetowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="0ac4a-112">W polu **Kredyt** podaj żądane wartości.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-112">In the **Credit** field, specify the desired values.</span></span> <span data-ttu-id="0ac4a-113">Zdefiniowane konto główne zastąpi konto główne strony kredytowej w wierszu załącznika arkusza oraz będzie również służyć do wycofywania odroczenia opartego na transakcjach naliczeń finansowych.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="0ac4a-114">W polu **Załącznik** wybierz sposób dobierania załącznika podczas księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-114">In the **Voucher** field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="0ac4a-115">W polu **Opis** wpisz wartość opisującą transakcje, które będą księgowane.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-115">In the **Description** field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="0ac4a-116">W polu **Częstotliwość okresu** wybierz, jak często mają mieć miejsce transakcje.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-116">In the **Period frequency** field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="0ac4a-117">W polu **Liczba wystąpień według okresu** wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-117">In the **Number of occurrences by period** field, enter a number.</span></span>
11. <span data-ttu-id="0ac4a-118">W polu **Księguj transakcje** wybierz, kiedy transakcje mają być księgowane, np. **Miesięcznie**.</span><span class="sxs-lookup"><span data-stu-id="0ac4a-118">In the **Post transactions** field, select when the transactions should be posted, such as **Monthly**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]