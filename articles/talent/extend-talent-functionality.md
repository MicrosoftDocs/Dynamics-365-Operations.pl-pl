---
title: Rozszerzanie funkcji programu Microsoft Dynamics 365 for Talent
description: "Po utworzeniu dowolnej aplikacji w środowisku Microsoft PowerApps można uruchomić takie aplikacje za pomocą łączy w programie Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: pl-pl
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a><span data-ttu-id="59a76-103">Rozszerzanie funkcji programu Microsoft Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="59a76-103">Extend the functionality of Microsoft Dynamics 365 for Talent</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="59a76-104">Po utworzeniu dowolnej aplikacji w środowisku Microsoft PowerApps można uruchomić takie aplikacje za pomocą łączy w programie Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="59a76-104">If you’ve created any Microsoft PowerApps, you can start those applications from links within Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="59a76-105">Aby skonfigurować dostęp do aplikacji, należy ustawić niektóre informacje w aplikacji Talent na stronie konfiguracji, którą można otworzyć z poziomu obszaru roboczego **Administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="59a76-105">To set up access to your applications, you’ll need to set up some information in Talent on a configuration page that you can open from the **System administration** workspace.</span></span>

## <a name="configuring-embedded-powerapps-within-talent"></a><span data-ttu-id="59a76-106">Konfiguracja osadzonych usług PowerApps w środowisku Talent</span><span class="sxs-lookup"><span data-stu-id="59a76-106">Configuring embedded PowerApps within Talent</span></span>
<span data-ttu-id="59a76-107">Na stronie **Ustaw osadzone usługi Microsoft PowerApps** można skonfigurować strony środowiska Talent do uruchamiania aplikacji PowerApps.</span><span class="sxs-lookup"><span data-stu-id="59a76-107">Use the **Set embedded Microsoft PowerApps** page to configure Talent pages to start PowerApps applications.</span></span> <span data-ttu-id="59a76-108">Aby otworzyć stronę **Ustaw osadzone usługi Microsoft PowerApps**, otwórz obszar roboczy **Administrowanie systemem**, a następnie otwórz kartę **Łącza**. Wybierz opcję **Microsoft PowerApps** z grupy **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="59a76-108">To open the **Set embedded Microsoft PowerApps** page, open the **System administration** workspace and then open the **Links** tab. Select **Microsoft PowerApps** from the **Setup** group.</span></span> 

<span data-ttu-id="59a76-109">Na tej stronie można wprowadzić lub ustawić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="59a76-109">The following information is entered or set on this page:</span></span> 

> - <span data-ttu-id="59a76-110">Nazwa opisowa lub identyfikator dla każdej aplikacji PowerApps.</span><span class="sxs-lookup"><span data-stu-id="59a76-110">A descriptive name or identifier for each PowerApps application.</span></span>
> - <span data-ttu-id="59a76-111">Niepowtarzalny identyfikator (GUID) dla każdej aplikacji dodawanej do strony Talent.</span><span class="sxs-lookup"><span data-stu-id="59a76-111">A unique identifier (GUID) for each application that you add to a Talent page.</span></span> <span data-ttu-id="59a76-112">Identyfikator aplikacji jest dostępny w witrynie usługi PowerApps [powerapps.com](http://powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="59a76-112">The app ID is available on the PowerApps site, [powerapps.com](http://powerapps.com/).</span></span> 
> - <span data-ttu-id="59a76-113">Strona, z której użytkownicy mogą otworzyć aplikację lub raport.</span><span class="sxs-lookup"><span data-stu-id="59a76-113">The page from which users can open an application or report.</span></span> <span data-ttu-id="59a76-114">Nie wszystkie strony środowiska Talent obsługują osadzone aplikacje PowerApps i raporty Power BI.</span><span class="sxs-lookup"><span data-stu-id="59a76-114">Not all Talent pages support embedded PowerApps and Power BI reports.</span></span> 

 > [!NOTE]
 >  <span data-ttu-id="59a76-115">Należy wprowadzić nazwę wewnętrzną strony, a nie nazwę wyświetlaną u góry strony.</span><span class="sxs-lookup"><span data-stu-id="59a76-115">Enter the internal name of the page, rather than the display name that appears at the top of the page.</span></span> <span data-ttu-id="59a76-116">Aby znaleźć nazwę wewnętrzną, otwórz stronę, której nazwy szukasz, i kliknij w dowolnym miejscu na stronie.</span><span class="sxs-lookup"><span data-stu-id="59a76-116">To find the internal name, open the page that you need the internal name of, and right-click anywhere on the page.</span></span> <span data-ttu-id="59a76-117">Po otwarciu menu, umieść kursor myszy nad pozycją **Informacje o formularzu**.</span><span class="sxs-lookup"><span data-stu-id="59a76-117">When the menu opens, hover over the **Form information** item.</span></span> <span data-ttu-id="59a76-118">Wewnętrzna nazwa formularza zostanie wyświetlona obok pozycji **Informacje o formularzu** w menu.</span><span class="sxs-lookup"><span data-stu-id="59a76-118">The internal form name is displayed next to the **Form information** item in the menu.</span></span>
 
> - <span data-ttu-id="59a76-119">Określ formant formularza, z którego aplikacja może pobrać dane kontekstowe.</span><span class="sxs-lookup"><span data-stu-id="59a76-119">Specify the form control from which the application can retrieve context data.</span></span> <span data-ttu-id="59a76-120">Aplikacja może na przykład używać danych na temat pracownika.</span><span class="sxs-lookup"><span data-stu-id="59a76-120">For example, an application might use data about a worker.</span></span> <span data-ttu-id="59a76-121">W przypadku wprowadzenia strony **Pracownik** w polu **Kontekst** przy uruchamianiu aplikacji będzie otwierana strona **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="59a76-121">If you enter the **Worker** page in the **Context** field, the **Worker** page will open when you start the application.</span></span> <span data-ttu-id="59a76-122">Wpis w **polu Kontekst** jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="59a76-122">An entry in the **Context field** is optional.</span></span> 
> - <span data-ttu-id="59a76-123">Ustaw rozmiar okna dialogowego, w którym będzie uruchamiana aplikacja PowerApps.</span><span class="sxs-lookup"><span data-stu-id="59a76-123">Set the size of the dialog box on which the PowerApps application will run.</span></span> <span data-ttu-id="59a76-124">Okna dialogowe są oznaczone jako „małe” lub „duże”, co umożliwia optymalizację interfejsu użytkownika, gdy aplikacja jest otwierana odpowiednio na telefonie lub większym urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="59a76-124">The dialog boxes are designated as “small” or “large” to optimize the user interface when your application for running on a phone or a larger device, respectively.</span></span> 

<span data-ttu-id="59a76-125">Można również określić firmy, dla których aplikacja będzie dostępne, lub udostępnić ją dla wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="59a76-125">You can also specify which legal entities an application will be available for, or you can make it available to all your legal entities.</span></span> <span data-ttu-id="59a76-126">Domyślnie aplikacje PowerApps są dostępne dla wszystkich firm.</span><span class="sxs-lookup"><span data-stu-id="59a76-126">By default, your PowerApps applications are available to all legal entities.</span></span>

## <a name="opening-an-application"></a><span data-ttu-id="59a76-127">Otwieranie aplikacji</span><span class="sxs-lookup"><span data-stu-id="59a76-127">Opening an application</span></span>
<span data-ttu-id="59a76-128">Po skonfigurowaniu osadzonych aplikacji PowerApps łącza do określonych aplikacji zostaną dodane do stron w środowisku Talent.</span><span class="sxs-lookup"><span data-stu-id="59a76-128">When you’ve configured embedded PowerApps applications, links to the applications that you specified will be added to the pages within Talent.</span></span> <span data-ttu-id="59a76-129">Aby otworzyć aplikację, kliknij łącze.</span><span class="sxs-lookup"><span data-stu-id="59a76-129">Click a link to open an application.</span></span> 



