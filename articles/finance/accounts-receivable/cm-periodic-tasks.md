---
title: Zadania okresowe zarządzania kredytami
description: W tym temacie opisano zadania okresowe, które są niezbędne w procesie zarządzania limitami kredytowymi dla odbiorców.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: df3b0b239fe542eab80fa92057248328d3f5188f
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015358"
---
# <a name="periodic-credit-management-tasks"></a><span data-ttu-id="30315-103">Zadania okresowe zarządzania kredytami</span><span class="sxs-lookup"><span data-stu-id="30315-103">Periodic credit management tasks</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="30315-104">W tym temacie opisano zadania okresowe, które są niezbędne w procesie zarządzania limitami kredytowymi dla odbiorców.</span><span class="sxs-lookup"><span data-stu-id="30315-104">This topic describes the periodic tasks that are a necessary part of the process of managing credit limits for customers.</span></span>

## <a name="update-risk-scores"></a><span data-ttu-id="30315-105">Aktualizuj oceny ryzyka</span><span class="sxs-lookup"><span data-stu-id="30315-105">Update risk scores</span></span>

<span data-ttu-id="30315-106">W miarę zmieniających się przedsiębiorstw i zmian okoliczności ryzyko kredytowe danego odbiorcy może również ulec zmianie.</span><span class="sxs-lookup"><span data-stu-id="30315-106">As businesses evolve and circumstances change, the credit risks for a given customer can also change.</span></span> <span data-ttu-id="30315-107">Aby ułatwić obsługę odpowiednich limitów kredytowych dla odbiorców, należy okresowo sprawdzać kryteria dla każdego wyniku ryzyka i aktualizować wyniki dla każdego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="30315-107">To help maintain appropriate credit limits for your customers, you must periodically review the criteria for each risk score and update the scores for each customer.</span></span> <span data-ttu-id="30315-108">Poniższe wyniki można zaktualizować, korzystając ze strony **Aktualizowanie wyników ryzyka** (**Kredyty i Windykacja \> Zadania okresowe \> Zarządzanie kredytem \> Aktualizowanie wyników ryzyka**).</span><span class="sxs-lookup"><span data-stu-id="30315-108">You can update the following scores by using the **Update risk scores** page (**Credit and collections \> Periodic tasks \> Credit management \> Update risk scores**).</span></span> <span data-ttu-id="30315-109">Przetwarzane są również wszystkie zdefiniowane przez użytkownika obliczenia.</span><span class="sxs-lookup"><span data-stu-id="30315-109">All user-defined calculations are also processed.</span></span>

- <span data-ttu-id="30315-110">**Średnia liczba dni płatności** — ten punkt jest średnią liczbą dni, przez jaką odbiorca może zapłacić faktury.</span><span class="sxs-lookup"><span data-stu-id="30315-110">**Average payment days** – This score is the average number of days that a customer takes to pay invoices.</span></span>
- <span data-ttu-id="30315-111">**Odbiorca od** — wartość tego pola to liczba lat, przez które odbiorca jest odbiorcą danej organizacji.</span><span class="sxs-lookup"><span data-stu-id="30315-111">**Customer since** – This score is the number of years that a customer has been a customer of your organization.</span></span>
- <span data-ttu-id="30315-112">**Działalność od** — jest to liczba lat, przez które odbiorca jest w trakcie działalności.</span><span class="sxs-lookup"><span data-stu-id="30315-112">**In business since** – This score is the number of years that a customer has been in business.</span></span> <span data-ttu-id="30315-113">Używana jest wartość pola **Rozpoczęcie działalności** na stronie **Odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="30315-113">It uses the value of the **Business start** field on the **Customers** page.</span></span>
- <span data-ttu-id="30315-114">**Wskaźnik rotacji należności w dniach** — ten wynik jest oparty na saldzie rozrachunków z odbiorcami, przychodach sprzedaży i liczbie dni w poprzednim okresie 12-miesięcznym.</span><span class="sxs-lookup"><span data-stu-id="30315-114">**Days sales outstanding** – This score is based on the accounts receivable balance, sales revenue, and number of days for the previous 12-month period.</span></span>
- <span data-ttu-id="30315-115">**Saldo średnie** — ten wynik jest oparty na saldzie rozrachunków z odbiorcami dla poprzedniego okresu 12-miesięcznego.</span><span class="sxs-lookup"><span data-stu-id="30315-115">**Average balance** – This score is based on the accounts receivable balance for the previous 12-month period.</span></span>
- <span data-ttu-id="30315-116">**Grupa zarządzania kredytami**, **Stan konta** i **Kraj** — te wyniki wykorzystują informacje od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="30315-116">**Credit management group**, **Account status**, and **Country** – These scores use information from the customer.</span></span>

## <a name="update-customer-balance-statistics"></a><span data-ttu-id="30315-117">Aktualizuj statystyki salda odbiorcy</span><span class="sxs-lookup"><span data-stu-id="30315-117">Update customer balance statistics</span></span>

<span data-ttu-id="30315-118">Istnieje możliwość uruchomienia procesu **Aktualizuj statystyki salda odbiorcy** w celu zaktualizowania obliczania statystyk salda wyświetlanego na stronie **Informacje o statystykach salda**.</span><span class="sxs-lookup"><span data-stu-id="30315-118">You can run the **Update customer balance statistics** process to update the calculation of balance statistics that is shown on the **Balance statistics inquiry** page.</span></span> <span data-ttu-id="30315-119">Te informacje służą do obliczania wyników ryzyka i wartości wyświetlanych w polach informacji statystycznych dotyczących odbiorcy na stronie **Odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="30315-119">This information is used to calculate risk scores and the values that are shown in the credit statistics FactBoxes on the **Customer** page.</span></span>

<span data-ttu-id="30315-120">Po uruchomieniu tego procesu system aktualizuje statystykę salda odbiorcy dla jednego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="30315-120">When you run the process, it updates customer balance statistics for a single customer.</span></span> <span data-ttu-id="30315-121">Aby skonfigurować zadanie przetwarzania wsadowego w celu uruchomienia procesu dla wielu odbiorców, można skorzystać ze strony **Oblicz statystykę salda** (**Zarządzanie kredytem \> Zadania okresowe \> Oblicz statystykę salda**).</span><span class="sxs-lookup"><span data-stu-id="30315-121">To set up a batch job to run the process for multiple customers, you can use the **Calculate balance statistics** page (**Credit management \> Periodic tasks \> Calculate balance statistics**).</span></span>
