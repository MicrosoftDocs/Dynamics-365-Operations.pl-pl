---
title: Użyczone składniki majątku
description: W tym temacie opisano sposób rejestrowania użyczonych składników majątku w Zarządzaniu składnikami majątku.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 712f3e7cdfb8d521ae2afb59d90bc5102da53cb7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813394"
---
# <a name="asset-loans"></a><span data-ttu-id="0ef30-103">Użyczone składniki majątku</span><span class="sxs-lookup"><span data-stu-id="0ef30-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0ef30-104">Jeśli Twoja firma otrzymuje aktywa do napraw lub prac konserwacyjnych z lokalizacji wewnętrznych lub od klientów, i jeśli tymczasowo pożyczasz aktywa do tych lokalizacji lub tym klientom, Zarządzanie składnikami majątku może śledzić użyczone składniki majątku.</span><span class="sxs-lookup"><span data-stu-id="0ef30-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="0ef30-105">Rejestracja użyczonych składników majątku w żądaniu konserwacji</span><span class="sxs-lookup"><span data-stu-id="0ef30-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="0ef30-106">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Żądania konserwacji** \> **Wszystkie żądania konserwacji** lub **Aktywne żądania konserwacji**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="0ef30-107">Wybierz żądanie konserwacji, aby zarejestrować użyczony składnik majątku, a następnie wybierz **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="0ef30-108">Na stronie **żądanie** wybierz opcję **Wyślij użyczony składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="0ef30-109">Wybierz składnik i wpisz oczekiwaną datę zwrotu.</span><span class="sxs-lookup"><span data-stu-id="0ef30-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="0ef30-110">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="0ef30-111">Użyczony składnik majątku można wysłać tylko wtedy, gdy jest dostępny składnik tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="0ef30-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="0ef30-112">Użyczany składnik majątku musi mieć stan cyklu życia pozwalający na użycie go jako użyczonego składnika majątku, np. **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="0ef30-113">Po zarejestrowaniu użyczonego składnika majątku jego cykl życia zostanie automatycznie zaktualizowany, np. **OnLoan.**</span><span class="sxs-lookup"><span data-stu-id="0ef30-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="0ef30-114">Aby wyświetlić listę wszystkich aktywów użyczonych innym lokalizacjom lub klientom, wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Użyczony składnik majątku** \> **Wszystkie użyczone składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="0ef30-115">Jeśli dla składnika majątku zaznaczono pole **Zakończono**, składnik majątku został zarejestrowany jako zwrócony Twojej firmie.</span><span class="sxs-lookup"><span data-stu-id="0ef30-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Zarządzanie żądaniami konserwacji](media/06-manage-maintenance-requests.png)

<span data-ttu-id="0ef30-117">Na stronie **Aktywne użyczone składniki majątku** można wyświetlić listę wszystkich użyczonych składników majątku, które nie zostały jeszcze zwrócone Twojej firmie.</span><span class="sxs-lookup"><span data-stu-id="0ef30-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="0ef30-118">Rejestrowanie użyczonych składników majątku jako zwróconych</span><span class="sxs-lookup"><span data-stu-id="0ef30-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="0ef30-119">Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Użyczony składnik majątku** \> **Aktywne użyczone składniki majątku**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="0ef30-120">Wybierz użyczony składnik majątku, który chcesz zarejestrować jako zwrócony, a następnie wybierz **Zwróć użyczony składnik majątku**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="0ef30-121">W polu **Zwrócone** wpisz datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="0ef30-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="0ef30-122">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ef30-122">Select **OK**.</span></span>
5. <span data-ttu-id="0ef30-123">Odśwież stronę listy **Aktywne użyczone składniki majątku**. Zauważ, że użyczonego składnika majątku już na niej nie ma.</span><span class="sxs-lookup"><span data-stu-id="0ef30-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]