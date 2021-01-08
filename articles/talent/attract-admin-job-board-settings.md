---
title: Włącz integrację z aplikacją Broadbean w Attract
description: W tym temacie opisano sposób konfigurowania rozwiązania Microsoft Dynamics 365 Talent - Attract w celu ogłaszania zadań w zewnętrznych tablicach zadań, takich jak Broadbean.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 10b612711e81b2b368ed23fdd95ab6a66451f0ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462293"
---
# <a name="enable-broadbean-integration-in-attract"></a><span data-ttu-id="26c6b-103">Włącz integrację z aplikacją Broadbean w Attract</span><span class="sxs-lookup"><span data-stu-id="26c6b-103">Enable Broadbean integration in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="26c6b-104">Chcesz dotrzeć z informacją o wakacie do jak największej liczby kandydatów posiadających odpowiednie kwalifikacje.</span><span class="sxs-lookup"><span data-stu-id="26c6b-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="26c6b-105">Serwisy rekrutacyjne, takie jak Broadbean mogą pomóc w osiągnięciu tych celów.</span><span class="sxs-lookup"><span data-stu-id="26c6b-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="26c6b-106">Microsoft Dynamics 365 Talent: Attract umożliwia teraz publikowanie ofert pracy na Broadbean, a Microsoft stale udostępnia nowe możliwości w tym zakresie.</span><span class="sxs-lookup"><span data-stu-id="26c6b-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

> [!NOTE]
> - <span data-ttu-id="26c6b-107">Aby opublikować oferty pracy na zewnętrznych stronach, musisz mieć [dodatek kompleksowej obsługi rekrutacji](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="26c6b-107">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="26c6b-108">Aby publikować oferty pracy w Broadbean za pośrednictwem Attract, należy posiadać subskrypcję Broadbean.</span><span class="sxs-lookup"><span data-stu-id="26c6b-108">To post jobs to Broadbean through Attract, you must have a Broadbean subscription.</span></span>
> - <span data-ttu-id="26c6b-109">Ta funkcja jest obecnie w wersjach zapoznawczych.</span><span class="sxs-lookup"><span data-stu-id="26c6b-109">This feature is currently in preview.</span></span> <span data-ttu-id="26c6b-110">Jeśli chcesz ją wypróbować, musisz najpierw [ją włączyć w ustawieniach administratora Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="26c6b-110">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

## <a name="configure-broadbean-integration"></a><span data-ttu-id="26c6b-111">Konfigurowanie integracji Broadbean</span><span class="sxs-lookup"><span data-stu-id="26c6b-111">Configure Broadbean integration</span></span>

1. <span data-ttu-id="26c6b-112">Zaloguj się w Attract jako administrator.</span><span class="sxs-lookup"><span data-stu-id="26c6b-112">Sign in to Attract as an admin.</span></span>

2. <span data-ttu-id="26c6b-113">Wybierz przycisk **ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie wybierz opcję **Centrum administracyjnego**.</span><span class="sxs-lookup"><span data-stu-id="26c6b-113">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>

3. <span data-ttu-id="26c6b-114">Skontaktuj się z Broadbean i wprowadź informacje w polach **Nazwa użytkownika**, **Identyfikator klienta** i **Token szyfrowania**.</span><span class="sxs-lookup"><span data-stu-id="26c6b-114">Contact Broadbean, and enter your information in the **Username**, **Client ID**, and **Encryption Token** fields.</span></span>

4. <span data-ttu-id="26c6b-115">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="26c6b-115">Select **Save**.</span></span>

> [!WARNING]
> <span data-ttu-id="26c6b-116">Twoje poświadczenia Broadbean są poufne.</span><span class="sxs-lookup"><span data-stu-id="26c6b-116">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="26c6b-117">W związku z tym przechowuj je z zachowaniem odpowiednich środków ostrożności.</span><span class="sxs-lookup"><span data-stu-id="26c6b-117">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="26c6b-118">Każda osoba z rolą administratora w Attract może wyświetlać te poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="26c6b-118">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="26c6b-119">Microsoft i Attract nie uczestniczą w tworzeniu ani przechowywaniu tych wartości.</span><span class="sxs-lookup"><span data-stu-id="26c6b-119">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="26c6b-120">Użytkownik ponosi odpowiedzialność za zachowanie aktualności danych w systemie Attract oraz współpracę z Broadbean w celu rozwiązywania wszelkich problemów związanych z jego poświadczeniami.</span><span class="sxs-lookup"><span data-stu-id="26c6b-120">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>
