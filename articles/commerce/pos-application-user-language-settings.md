---
title: Ustawienia języka użytkownika i aplikacji POS
description: W tym temacie opisano, jak zmienić ustawienia języka w programach Modern POS (MPOS) i Cloud POS.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bdd03dff359e7c2799eff53b0e999580ce8b1c06
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193110"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="59097-103">Ustawienia języka użytkownika i aplikacji POS</span><span class="sxs-lookup"><span data-stu-id="59097-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="59097-104">W tym temacie opisano, jak zmienić ustawienia języka w programach Modern POS (MPOS) i Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="59097-104">This topic describes how to change language settings in Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="59097-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="59097-105">Overview</span></span>
<span data-ttu-id="59097-106">Programy Modern POS (MPOS) i Cloud POS obsługują środowiska, w których ustawienia językowe i tłumaczenia mogą się różnić w zależności od sklepu i ustawień użytkownika.</span><span class="sxs-lookup"><span data-stu-id="59097-106">Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="59097-107">Na przykład sklep może znajdować się regionie, w którym głównym językiem odbiorców jest angielski, ale niektórzy pracownicy wolą korzystać z aplikacji w języku francuskim.</span><span class="sxs-lookup"><span data-stu-id="59097-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="59097-108">Język danych</span><span class="sxs-lookup"><span data-stu-id="59097-108">Data language</span></span>

<span data-ttu-id="59097-109">Niezależnie od ustawień programy MPOS i Cloud POS zawsze używają ustawień języka sklepu do tłumaczenia danych.</span><span class="sxs-lookup"><span data-stu-id="59097-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="59097-110">To zapewnia spójność środowiska dla wszystkich użytkowników i odbiorców.</span><span class="sxs-lookup"><span data-stu-id="59097-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="59097-111">Przykładowe dane:</span><span class="sxs-lookup"><span data-stu-id="59097-111">Examples of data include:</span></span>

- <span data-ttu-id="59097-112">Produkty</span><span class="sxs-lookup"><span data-stu-id="59097-112">Products</span></span>
- <span data-ttu-id="59097-113">Atrybuty i wartości</span><span class="sxs-lookup"><span data-stu-id="59097-113">Attributes and values</span></span>
- <span data-ttu-id="59097-114">Nazwy kategorii</span><span class="sxs-lookup"><span data-stu-id="59097-114">Category names</span></span>
- <span data-ttu-id="59097-115">Drukowane lub wysyłane e-mailem potwierdzenia transakcji</span><span class="sxs-lookup"><span data-stu-id="59097-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="59097-116">Nazwy metod płatności</span><span class="sxs-lookup"><span data-stu-id="59097-116">Payment method names</span></span>
- <span data-ttu-id="59097-117">Komunikaty wyświetlacza wierszowego</span><span class="sxs-lookup"><span data-stu-id="59097-117">Line display messages</span></span>

<span data-ttu-id="59097-118">Język sklepu będzie również używany na głównym ekranie logowania w punkcie sprzedaży, ponieważ przed zalogowaniem użytkownik nie jest znany.</span><span class="sxs-lookup"><span data-stu-id="59097-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="59097-119">Jeśli tłumaczenie nie jest dostępne w języku sklepu, będzie używany język firmy.</span><span class="sxs-lookup"><span data-stu-id="59097-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="59097-120">Konfigurowanie ustawień języka dla sklepu</span><span class="sxs-lookup"><span data-stu-id="59097-120">Configuring the store's language setting</span></span>

<span data-ttu-id="59097-121">Język sklepu ustawia się w obszarze **Wszystkie sklepy** na stronie **Sklep** w menu **Ogólne &gt; Ustawienia regionalne &gt; Język**.</span><span class="sxs-lookup"><span data-stu-id="59097-121">The store's language setting is set from **All stores** on the **Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="59097-122">Wybierz język dla każdego sklepu z listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="59097-122">Use the drop-down list to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="59097-123">Język interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="59097-123">User interface language</span></span>

<span data-ttu-id="59097-124">Ustawienie języka użytkownika punktu sprzedaży określa tłumaczenia używane w interfejsie użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="59097-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="59097-125">Obejmuje to wszystkie etykiety, menu i listy, które nie są danymi.</span><span class="sxs-lookup"><span data-stu-id="59097-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="59097-126">Jedynym wyjątkiem jest tekst wyświetlany na siatce przycisków punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="59097-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="59097-127">Dla siatek przycisków nie są dostępne tłumaczenia, więc będą one zawsze wyświetlane zgodnie z konfiguracją przycisku.</span><span class="sxs-lookup"><span data-stu-id="59097-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="59097-128">Aby włączyć tłumaczenia przycisków, trzeba skopiować i zachować siatki przycisków i przypisać je do użytkowników według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="59097-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="59097-129">Konfigurowanie ustawień języka użytkownika</span><span class="sxs-lookup"><span data-stu-id="59097-129">Configuring the user's language setting</span></span>

<span data-ttu-id="59097-130">Język użytkownika punktu sprzedaży ustawia się w obszarze **Wszyscy pracownicy** na stronie **Pracownik** w menu **Handel detaliczny i inny &gt; Język**.</span><span class="sxs-lookup"><span data-stu-id="59097-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail and Commerce &gt; Language**.</span></span> <span data-ttu-id="59097-131">Nie da się go ustawić na karcie Profil. To ustawienie jest używane w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="59097-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="59097-132">Jeśli nie ustawiono języka użytkownika lub tłumaczenia w wybranym języku są niedostępne, ustawienia językowe w punkcie sprzedaży wrócą do języka sklepu.</span><span class="sxs-lookup"><span data-stu-id="59097-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

| &nbsp;      | <span data-ttu-id="59097-133">Język interfejsu użytkownika  </span><span class="sxs-lookup"><span data-stu-id="59097-133">UI language</span></span>                | <span data-ttu-id="59097-134">Język danych (produkty, formaty paragonów, wyświetlacz wierszowy itp.)</span><span class="sxs-lookup"><span data-stu-id="59097-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="59097-135">**Firma**</span><span class="sxs-lookup"><span data-stu-id="59097-135">**Company**</span></span> | <span data-ttu-id="59097-136">Domyślna</span><span class="sxs-lookup"><span data-stu-id="59097-136">Default</span></span>                    | <span data-ttu-id="59097-137">Domyślna</span><span class="sxs-lookup"><span data-stu-id="59097-137">Default</span></span>                                                       |
| <span data-ttu-id="59097-138">**Sklep**</span><span class="sxs-lookup"><span data-stu-id="59097-138">**Store**</span></span>   | <span data-ttu-id="59097-139">Zastępuje ustawienie dla firmy</span><span class="sxs-lookup"><span data-stu-id="59097-139">Overrides company</span></span>          | <span data-ttu-id="59097-140">Zastępuje ustawienie dla firmy</span><span class="sxs-lookup"><span data-stu-id="59097-140">Overrides company</span></span>                                             |
| <span data-ttu-id="59097-141">**Użytkownik**</span><span class="sxs-lookup"><span data-stu-id="59097-141">**User**</span></span>    | <span data-ttu-id="59097-142">Zastępuje ustawienie dla sklepu lub firmy</span><span class="sxs-lookup"><span data-stu-id="59097-142">Overrides store or company</span></span> | <span data-ttu-id="59097-143">Nigdy</span><span class="sxs-lookup"><span data-stu-id="59097-143">Never</span></span>                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]