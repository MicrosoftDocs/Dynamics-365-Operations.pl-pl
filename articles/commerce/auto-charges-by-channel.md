---
title: Włączanie i konfigurowanie opłat automatycznych według kanałów
description: W tym temacie wyjaśniono, jak włączyć i skonfigurować opłaty automatyczne według kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 23d02cf96faf3753303435acc148bf71e487d791
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799926"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="7f185-103">Włączanie i konfigurowanie opłat automatycznych według kanałów</span><span class="sxs-lookup"><span data-stu-id="7f185-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="7f185-104">W tym temacie wyjaśniono, jak włączyć i skonfigurować opłaty automatyczne (auto opłaty) według kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7f185-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7f185-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="7f185-105">Overview</span></span>

<span data-ttu-id="7f185-106">Może istnieć sytuacja, w której opłaty za recykling lub inne opłaty muszą być stosowane do grupy produktów sprzedawanych we wszystkich lub niektórych sklepach w określonym stanie (np. w Kalifornii).</span><span class="sxs-lookup"><span data-stu-id="7f185-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="7f185-107">Funkcja **Włącz filtrowanie opłat automatycznych według kanałów** w module Commerce umożliwia określenie automatycznych opłat według kanałów (na przykład: konkretny sklepu fizycznego).</span><span class="sxs-lookup"><span data-stu-id="7f185-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="7f185-108">Ta funkcja jest włączana w Dynamics 365 Commerce wersja 10.0.10 i nowsze.</span><span class="sxs-lookup"><span data-stu-id="7f185-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="7f185-109">Aby włączyć i skonfigurować opłaty automatyczne według kanałów, należy wykonać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="7f185-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="7f185-110">Włącz funkcję **Włącz filtrowanie automatycznych opłat według kanałów**.</span><span class="sxs-lookup"><span data-stu-id="7f185-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="7f185-111">Skonfiguruj cel hierarchii organizacyjnej.</span><span class="sxs-lookup"><span data-stu-id="7f185-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="7f185-112">Definiuj opłaty automatyczne według kanałów.</span><span class="sxs-lookup"><span data-stu-id="7f185-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="7f185-113">Funkcja **Włącz filtrowanie automatycznych opłat według kanałów** działa tylko wtedy, gdy włączona jest również funkcja zaawansowane opłaty automatyczne.</span><span class="sxs-lookup"><span data-stu-id="7f185-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="7f185-114">Aby uzyskać informacje dotyczące włączania funkcji zaawansowanych opłat automatycznych, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="7f185-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="7f185-115">Włącz funkcję Włącz filtrowanie automatycznych opłat według kanałów</span><span class="sxs-lookup"><span data-stu-id="7f185-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="7f185-116">Aby włączyć automatyczne opłaty według kanału w module Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7f185-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7f185-117">Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="7f185-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="7f185-118">Na karcie **Niewłączone**, na liście **Nazwa funkcji** znajdź i zaznacz opcję **Włącz filtrowanie automatycznych opłat według kanałów**.</span><span class="sxs-lookup"><span data-stu-id="7f185-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="7f185-119">W prawym dolnym rogu wybierz opcję **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="7f185-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="7f185-120">Po włączeniu tej funkcji zostanie ona wyświetlona na liście na karcie **Wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="7f185-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="7f185-121">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="7f185-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="7f185-122">W lewym okienku znajdź i zaznacz zadanie **1110** (**Konfiguracja globalna**).</span><span class="sxs-lookup"><span data-stu-id="7f185-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="7f185-123">W okienku akcji wybierz opcję **Uruchom teraz**, aby propagować zmiany konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7f185-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="7f185-124">Jeśli po wywłączeniu funkcji **Włącz filtrowanie automatycznych opłat według kanałów** po jej użyciu, pole **Relacja kanału detalicznego** w obszarze **Automatyczne opłaty** nie będzie już wyświetlane i wszystkie istniejące konfiguracje zostaną utracone.</span><span class="sxs-lookup"><span data-stu-id="7f185-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="7f185-125">Jeśli usunięcie **Relacji kanału detalicznego** spowoduje, że reguły automatycznego pobierania opłat zostaną zduplikowane, próba wyłączenia tej funkcji nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="7f185-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="7f185-126">Przed wyłączeniem tej funkcji należy sprawdzić wszystkie reguły automatycznego pobierania opłat i wprowadzić wszelkie wymagane zmiany.</span><span class="sxs-lookup"><span data-stu-id="7f185-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="7f185-127">Skonfiguruj cel hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="7f185-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="7f185-128">Utworzono nowy cel hierarchii organizacyjnej o nazwie **Automatyczne opłaty detaliczne** w celu zarządzania hierarchią opłat automatycznych według kanałów.</span><span class="sxs-lookup"><span data-stu-id="7f185-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="7f185-129">Aby przypisać hierarchię domyślną do celu hierarchii organizacyjnej w module Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7f185-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="7f185-130">Wybierz kolejno opcje **Administrowanie organizacją \> Organizacje \> Cele hierarchii organizacyjnej**.</span><span class="sxs-lookup"><span data-stu-id="7f185-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="7f185-131">W lewym okienku wybierz opcję **Automatyczne opłaty detaliczne**.</span><span class="sxs-lookup"><span data-stu-id="7f185-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="7f185-132">W obszarze **Przypisane hierarchie** wybierzopcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="7f185-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="7f185-133">W oknie dialogowym **Hierarchie organizacji** wybierz hierarchię organizacyjną (np. **Sklepy detaliczne według regionów**), a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f185-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="7f185-134">W obszarze **Przypisane hierarchie** wybierzopcję **Ustaw jako domyślny**.</span><span class="sxs-lookup"><span data-stu-id="7f185-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="7f185-135">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="7f185-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="7f185-136">W lewym okienku znajdź i zaznacz zadanie **1040** (**Produkty**).</span><span class="sxs-lookup"><span data-stu-id="7f185-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="7f185-137">W okienku akcji wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="7f185-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="7f185-138">Powtórz dwa poprzednie kroki, aby uruchomić zadania **1070** (**konfiguracja kanału**) i **1110** (**konfiguracja globalna**).</span><span class="sxs-lookup"><span data-stu-id="7f185-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Konfiguracja celu hierarchii automatycznej opłaty w organizacji sieci sprzedaży](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="7f185-140">Definiuj opłaty automatyczne według kanałów</span><span class="sxs-lookup"><span data-stu-id="7f185-140">Define auto charges by channel</span></span>

<span data-ttu-id="7f185-141">Po włączeniu funkcji **Włącz filtrowanie automatycznych opłat według kanałów** i skonfigurowaniu celu hierarchii organizacja **Automatyczne opłaty detaliczne** można zdefiniować automatyczne opłaty według kanałów na poziomie nagłówka zamówienia lub na poziomie wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7f185-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="7f185-142">Aby zdefiniować automatyczne opłaty według kanału w module Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7f185-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7f185-143">Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia opłat \> Opłaty automatyczne**.</span><span class="sxs-lookup"><span data-stu-id="7f185-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="7f185-144">W lewym okienku w polu **Poziom** wybierz opcję **Nagłówek** lub **Wiersz**, w zależności od wymagań biznesowych.</span><span class="sxs-lookup"><span data-stu-id="7f185-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="7f185-145">W polu **Kod kanału sprzedaży** wybierz odpowiedni kod kanału (np. **tabelę** lub **grupę**).</span><span class="sxs-lookup"><span data-stu-id="7f185-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="7f185-146">Jeśli ustawienie domyślne, **Wszystkie**, jest używana, reguły opłat są stosowane do wszystkich kanałów.</span><span class="sxs-lookup"><span data-stu-id="7f185-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="7f185-147">W przypadku wybrania opcji **Grupa** należy się upewnić, że Grupa opłat kanału sprzedaży jest tworzona w **Retail i Commerce \> Ustawienia kanału \> Opłaty \> Grupy opłat kanałów detalicznych**.</span><span class="sxs-lookup"><span data-stu-id="7f185-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="7f185-148">W przypadku wybrania opcji **Tabela** można wybrać konkretny kanał (np. **San Francisco**) w polu **Relacja kanału detalicznego**.</span><span class="sxs-lookup"><span data-stu-id="7f185-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="7f185-149">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="7f185-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="7f185-150">W lewym okienku znajdź i zaznacz zadanie **1040** (**Produkty**).</span><span class="sxs-lookup"><span data-stu-id="7f185-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="7f185-151">W okienku akcji wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="7f185-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="7f185-152">Powtórz dwa poprzednie kroki, aby uruchomić zadania **1070** (**konfiguracja kanału**) i **1110** (**konfiguracja globalna**).</span><span class="sxs-lookup"><span data-stu-id="7f185-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Zdefiniowane opłaty automatyczne według kanałów](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="7f185-154">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="7f185-154">Example scenario</span></span>

<span data-ttu-id="7f185-155">W poniższym przykładzie przedstawiono kroki wymagane do skonfigurowania produktu, tak aby opłaty za recykling były naliczane, gdy produkt jest sprzedawany za pośrednictwem kanału San Francisco sklepu fizycznego.</span><span class="sxs-lookup"><span data-stu-id="7f185-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="7f185-156">W przykładzie pokazano również, w jaki sposób automatycznie opłaty są wyświetlane w punkcie sprzedaży Commerce (POS).</span><span class="sxs-lookup"><span data-stu-id="7f185-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="7f185-157">W organizacji definiowany jest kod opłat o nazwie **RECYKLING**, co pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="7f185-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Kod opłat za RECYKLING](media/Auto-charges-charge-code.png)

<span data-ttu-id="7f185-159">Automatyczna opłata jest utworzona na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="7f185-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="7f185-160">Ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="7f185-160">It has the following configuration:</span></span>

- <span data-ttu-id="7f185-161">W polu **Kod konta** jest ustawiona wartość **Wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="7f185-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="7f185-162">W polu **Kod pozycji** jest ustawiona wartość **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="7f185-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="7f185-163">Pole **Relacja pozycji** ma wartość identyfikatora produktu **91001**.</span><span class="sxs-lookup"><span data-stu-id="7f185-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="7f185-164">W polu **Kod metody dostawy** jest ustawiona wartość **Wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="7f185-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="7f185-165">W polu **Kod kanału sprzedaży** jest ustawiona wartość **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="7f185-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="7f185-166">Pole **Relacja kanału detalicznego** jest ustawione na sklep **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="7f185-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="7f185-167">Utworzono wiersz opłat automatycznych.</span><span class="sxs-lookup"><span data-stu-id="7f185-167">An auto charges line is created.</span></span> <span data-ttu-id="7f185-168">Ma następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="7f185-168">It has the following configuration:</span></span>

- <span data-ttu-id="7f185-169">Pole **Waluta** ma ustawioną wartość **USD**.</span><span class="sxs-lookup"><span data-stu-id="7f185-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="7f185-170">W polu **Kod opłat** jest ustawiona wartość **RECYKLING**.</span><span class="sxs-lookup"><span data-stu-id="7f185-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="7f185-171">W polu **Kategoria** jest ustawiona wartość **Ustawiona**.</span><span class="sxs-lookup"><span data-stu-id="7f185-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="7f185-172">Pole **Opłaty** ma ustawioną wartość **$6.25**.</span><span class="sxs-lookup"><span data-stu-id="7f185-172">The **Charges** field is set to **$6.25**.</span></span>

![Konfiguracja automatycznej opłaty na poziomie wiersza i wiersza opłat automatycznych](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="7f185-174">W aplikacji POS zamówienie sprzedaży jest tworzone w kanale sklepu **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="7f185-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="7f185-175">Wiersz **Opłat** zawiera opłatę za recykling **$6,25**.</span><span class="sxs-lookup"><span data-stu-id="7f185-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="7f185-176">Po wybraniu **Opcje transakcji \> Opłaty \> Zarządzaj opłatami** w aplikacji punktu sprzedaży, można wyświetlić kod opłat i opis opłaty za recykling.</span><span class="sxs-lookup"><span data-stu-id="7f185-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Opłata za recykling w aplikacji punktu sprzedaży](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="7f185-178">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="7f185-178">Additional resources</span></span>

[<span data-ttu-id="7f185-179">Wielokanałowe zaawansowane opłaty automatyczne</span><span class="sxs-lookup"><span data-stu-id="7f185-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="7f185-180">Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży</span><span class="sxs-lookup"><span data-stu-id="7f185-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]