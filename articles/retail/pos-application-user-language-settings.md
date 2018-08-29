---
title: "Ustawienia języka użytkownika i aplikacji POS"
description: "W tym temacie opisano, jak zmienić ustawienia języka w programach Retail Modern POS (MPOS) i Cloud POS."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 1ea4309d57a7b6b4ca4ae3fdd995c95d93c5c080
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="f3b38-103">Ustawienia języka użytkownika i aplikacji POS</span><span class="sxs-lookup"><span data-stu-id="f3b38-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3b38-104">W tym temacie opisano, jak zmienić ustawienia języka w programach Retail Modern POS (MPOS) i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="f3b38-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="f3b38-105">Przegląd</span><span class="sxs-lookup"><span data-stu-id="f3b38-105">Overview</span></span>
<span data-ttu-id="f3b38-106">Programy Modern POS (MPOS) i Cloud POS obsługują środowiska, w których ustawienia językowe i tłumaczenia mogą się różnić w zależności od sklepu i ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f3b38-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="f3b38-107">Na przykład sklep może znajdować się regionie, w którym głównym językiem odbiorców jest angielski, ale niektórzy pracownicy wolą korzystać z aplikacji w języku francuskim.</span><span class="sxs-lookup"><span data-stu-id="f3b38-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="f3b38-108">Język danych</span><span class="sxs-lookup"><span data-stu-id="f3b38-108">Data language</span></span>
<span data-ttu-id="f3b38-109">Niezależnie od ustawień programy MPOS i Cloud POS zawsze używają ustawień języka sklepu do tłumaczenia danych.</span><span class="sxs-lookup"><span data-stu-id="f3b38-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="f3b38-110">To zapewnia spójność środowiska dla wszystkich użytkowników i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="f3b38-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="f3b38-111">Przykładowe dane:</span><span class="sxs-lookup"><span data-stu-id="f3b38-111">Examples of data include:</span></span>

-   <span data-ttu-id="f3b38-112">Produkty</span><span class="sxs-lookup"><span data-stu-id="f3b38-112">Products</span></span>
-   <span data-ttu-id="f3b38-113">Atrybuty i wartości</span><span class="sxs-lookup"><span data-stu-id="f3b38-113">Attributes and values</span></span>
-   <span data-ttu-id="f3b38-114">Nazwy kategorii</span><span class="sxs-lookup"><span data-stu-id="f3b38-114">Category names</span></span>
-   <span data-ttu-id="f3b38-115">Drukowane lub wysyłane e-mailem potwierdzenia transakcji</span><span class="sxs-lookup"><span data-stu-id="f3b38-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="f3b38-116">Nazwy metod płatności</span><span class="sxs-lookup"><span data-stu-id="f3b38-116">Payment method names</span></span>
-   <span data-ttu-id="f3b38-117">Komunikaty wyświetlacza wierszowego</span><span class="sxs-lookup"><span data-stu-id="f3b38-117">Line display messages</span></span>

<span data-ttu-id="f3b38-118">Język sklepu będzie również używany na głównym ekranie logowania w punkcie sprzedaży, ponieważ przed zalogowaniem użytkownik nie jest znany.</span><span class="sxs-lookup"><span data-stu-id="f3b38-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="f3b38-119">Jeśli tłumaczenie nie jest dostępne w języku sklepu, będzie używany język firmy.</span><span class="sxs-lookup"><span data-stu-id="f3b38-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="f3b38-120">Konfigurowanie ustawień języka dla sklepu</span><span class="sxs-lookup"><span data-stu-id="f3b38-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="f3b38-121">Język sklepu ustawia się w obszarze **Wszystkie sklepy sieci sprzedaży** na stronie **Sklep sieci sprzedaży”** w menu **Ogólne &gt; Ustawienia regionalne &gt; Język.</span><span class="sxs-lookup"><span data-stu-id="f3b38-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="f3b38-122">**Wybierz język dla każdego sklepu z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="f3b38-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="f3b38-123">Język interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="f3b38-123">User interface language</span></span>
<span data-ttu-id="f3b38-124">Ustawienie języka użytkownika punktu sprzedaży określa tłumaczenia używane w interfejsie użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="f3b38-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="f3b38-125">Obejmuje to wszystkie etykiety, menu i listy, które nie są danymi.</span><span class="sxs-lookup"><span data-stu-id="f3b38-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="f3b38-126">Jedynym wyjątkiem jest tekst wyświetlany na siatce przycisków punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3b38-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="f3b38-127">Dla siatek przycisków nie są dostępne tłumaczenia, więc będą one zawsze wyświetlane zgodnie z konfiguracją przycisku.</span><span class="sxs-lookup"><span data-stu-id="f3b38-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="f3b38-128">Aby włączyć tłumaczenia przycisków, trzeba skopiować i zachować siatki przycisków i przypisać je do użytkowników według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="f3b38-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="f3b38-129">Konfigurowanie ustawień języka użytkownika</span><span class="sxs-lookup"><span data-stu-id="f3b38-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="f3b38-130">Język użytkownika punktu sprzedaży ustawia się w obszarze **Wszyscy pracownicy** na stronie **Pracownik** w menu **Handel detaliczny &gt; Język**.</span><span class="sxs-lookup"><span data-stu-id="f3b38-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="f3b38-131">Nie da się go ustawić na karcie Profil. To ustawienie jest używane w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="f3b38-131">It is not set on the main Profile tab.  This setting is not used by POS.</span></span> <span data-ttu-id="f3b38-132">Jeśli nie ustawiono języka użytkownika lub tłumaczenia w wybranym języku są niedostępne, ustawienia językowe w punkcie sprzedaży wrócą do języka sklepu.</span><span class="sxs-lookup"><span data-stu-id="f3b38-132">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="f3b38-133">** **</span><span class="sxs-lookup"><span data-stu-id="f3b38-133">** **</span></span>       | <span data-ttu-id="f3b38-134">**Język interfejsu użytkownika** ** **</span><span class="sxs-lookup"><span data-stu-id="f3b38-134">**UI language** ** **</span></span>      | <span data-ttu-id="f3b38-135">**Język danych (produkty, formaty paragonów, wyświetlacz wierszowy itp.)**</span><span class="sxs-lookup"><span data-stu-id="f3b38-135">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="f3b38-136">**Firma**</span><span class="sxs-lookup"><span data-stu-id="f3b38-136">**Company**</span></span> | <span data-ttu-id="f3b38-137">Domyślna</span><span class="sxs-lookup"><span data-stu-id="f3b38-137">Default</span></span>                    | <span data-ttu-id="f3b38-138">Domyślna</span><span class="sxs-lookup"><span data-stu-id="f3b38-138">Default</span></span>                                                           |
| <span data-ttu-id="f3b38-139">**Sklep**</span><span class="sxs-lookup"><span data-stu-id="f3b38-139">**Store**</span></span>   | <span data-ttu-id="f3b38-140">Zastępuje ustawienie dla firmy</span><span class="sxs-lookup"><span data-stu-id="f3b38-140">Overrides company</span></span>          | <span data-ttu-id="f3b38-141">Zastępuje ustawienie dla firmy</span><span class="sxs-lookup"><span data-stu-id="f3b38-141">Overrides company</span></span>                                                 |
| <span data-ttu-id="f3b38-142">**Użytkownik**</span><span class="sxs-lookup"><span data-stu-id="f3b38-142">**User**</span></span>    | <span data-ttu-id="f3b38-143">Zastępuje ustawienie dla sklepu lub firmy</span><span class="sxs-lookup"><span data-stu-id="f3b38-143">Overrides store or company</span></span> | <span data-ttu-id="f3b38-144">Nigdy</span><span class="sxs-lookup"><span data-stu-id="f3b38-144">Never</span></span>                                                             |






