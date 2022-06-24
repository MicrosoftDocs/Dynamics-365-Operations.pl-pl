---
title: Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL
description: W tym artykule opisano, jak skonfigurować stronę handlu elektronicznego Microsoft Dynamics 365 Commerce, która może obsługiwać zawartość dynamiczną na podstawie parametrów adresu URL.
author: StuHarg
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.openlocfilehash: e2b13403ffb316059476a03857c849b4f9f8cb9c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884670"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym artykule opisano, jak skonfigurować stronę handlu elektronicznego Microsoft Dynamics 365 Commerce, która może obsługiwać zawartość dynamiczną na podstawie parametrów adresu URL.

Stronę w usługach handlu elektronicznego można skonfigurować tak, aby obsługiowała inną zawartość, w zależności od segmentu w ścieżce adresu URL. Dlatego strona jest znana jako strona dynamiczna. Segment jest używany jako parametr pobierania zawartości strony. Na przykład strona utworzona w programie budującym witrynę i nazwana **blog\_viewer** zostanie zmapowana do adresu URL `https://fabrikam.com/blog`. Następnie można użyć tej strony, aby wyświetlić inną zawartość, opartą na ostatnim segmencie ścieżki adresu URL. Na przykład ostatnim segmentem adresu URL `https://fabrikam.com/blog/article-1` jest **artykuł-1**.

Możesz także zastąpić sparametryzowany segment URL stroną budowania witryny. Na przykład strona utworzona w programie budującym witrynę i nazwana **blog\_summary** może być zmapowana do adresu URL `https://fabrikam.com/blog/about-this-blog`. Kiedy żądany jest URL `https://fabrikam.com/blog` z segmentem `/about-this-blog` na końcu, zwracana jest zawartość strony **blog\_summary**, zamiast segmentu `/about-this-blog` interpretowanego jako parametr do użycia przez stronę `https://fabrikam.com/blog`. 

Wybierając nazwy parametrów, które mają być przekazane stronie dynamicznej, nie można używać nazwy strony dynamicznej w postaci, w jakiej występuje ona w adresie URL (`/blog` w powyższym przykładzie), jako nazwy parametru lub podłańcucha nazwy parametru. 

> [!NOTE]
> Funkcjonalność hostingu, pobierania i wyświetlania dynamicznej zawartości strony jest implementowana przy użyciu modułu niestandardowego. Więcej informacji jest dostępnych w artykule [Rozszerzanie kanału online](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Skonfiguruj dynamiczną stronę handlu elektronicznego

Aby skonfigurować dynamiczną stronę handlu elektronicznego, musisz utworzyć stronę dynamiczną, utworzyć podstawowy adres URL i skonfigurować trasę do strony dynamicznej.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Utwórz stronę, która będzie obsługi zawartości dynamicznej

Aby utworzyć stronę, która będzie obsługiwać zawartość dynamiczną, wykonaj kroki w witrynie [Dodawanie nowej strony witryny](add-new-page.md). Utworzona strona będzie wymagała implementacji modułu, który używa ostatniego segmentu ścieżki URL do pobierania treści z zewnętrznego źródła danych. Aby uzyskać więcej informacji dotyczących tworzenia modułów niestandardowych, zobacz [Możliwości rozszerzania kanału online](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Utwórz podstawowy adres URL strony dynamicznej

Aby utworzyć podstawowy adres URL strony dynamicznej w Konstruktorze witryn Commerce, wykonaj następujące kroki.

1. Przejdź do obszaru **Adresy URL**, a następnie wybierz pozycję **Nowy \> Nowy adres URL**.
1. W oknie dialogowym **Tworzenie nowego adresu URL** wybierz pozycję **Strona wewnętrzna**. W obszarze **Ścieżka adresu URL** wprowadź ścieżkę, która będzie pełnić funkcję katalogu głównego strony dynamicznej (w tym przykładzie jest to **/blog**). Następnie kliknij przycisk **Dalej**.
1. W oknie dialogowym **Wybieranie strony** wybierz utworzoną przez siebie stronę, która ma służyć jako strona dynamiczna, a następnie wybierz **Zapisz**.
1. Wybierz opcję **Publikuj**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Konfigurowanie marszruty do strony dynamicznej

Aby skonfigurować trasę do strony dynamicznej w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. W obszarze **Ścieżki parametrów adresu URL** wybierz opcję **Dodaj**, a następnie wprowadź ścieżkę URL wprowadzona podczas tworzenia adresu URL (w tym przykładzie jest to **/blog**).
1. Wybierz **Zapisz i opublikuj**.

Po skonfigurowaniu trasy wszystkie żądania skierowane do sparametryzowanej ścieżki adresu URL spowodują zwrócenie strony skojarzonej z tym adresem URL. Jeśli jakiekolwiek żądania zawierają dodatkowy segment, skojarzona strona zostanie zwrócona, a zawartość strony zostanie pobrana przy użyciu segmentu jako parametru. Na przykład `https://fabrikam.com/blog/article-1` zwróci stronę `https://fabrikam.com/blog` wyświetlającą treść, którą pobrano przy użyciu parametru **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Zastąp sparametryzowany adres URL stroną niestandardową

Aby zastąpić sparametryzowany adres URL niestandardową stroną w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do obszaru **Adresy URL**, a następnie wybierz pozycję **Nowy \> Nowy adres URL**.
1. W oknie dialogowym **Tworzenie nowego adresu URL** wybierz pozycję **Strona wewnętrzna**. W obszarze **Ścieżka adresu URL** wprowadź ścieżkę, która zawiera segment, który ma być zastąpiony (w tym przykładzie jest to **/blog/about-this-blog**). Następnie kliknij przycisk **Dalej**.
1. W oknie dialogowym **Wybierz stronę** wybierz stronę niestandardową, a następnie wybierz pozycję **Zapisz**.
1. Wybierz opcję **Publikuj**.
1. Jeśli strona niestandardowa nie została jeszcze opublikowana, przejdź na **Strony**, wybierz niestandardową stronę, a następnie wybierz pozycję **Publikuj**.

Po opublikowaniu strony niestandardowej będzie ona wyświetlana zamiast strony dynamicznej, która ma sparametryzowaną zawartość.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Modyfikacja istniejącej strony witryny](modify-existing-page.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Wybieranie układów stron](select-page-layouts.md)

[Zarządzanie metadanymi SEO](manage-seo-metadata.md)

[Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md)

[Wzbogacanie strony produktu](enrich-product-page.md)

[Wzbogacanie strony docelowej kategorii](enrich-category-page.md)

[Weryfikowanie dostępności zawartości strony](verify-accessibility.md)

[Rozszerzanie kanału online](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
