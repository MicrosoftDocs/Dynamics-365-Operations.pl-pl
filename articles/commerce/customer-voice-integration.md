---
title: Integruj usługę Customer Voice ze stronami witryny handlu elektronicznego
description: W tym artykule opisano, jak zintegrować Microsoft Dynamics 365 Customer Voice ze stronami witryny e-commerce Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: c8c67ecf4950c92fc91c8d119e06e5e8afff0ddf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850337"
---
# <a name="integrate-customer-voice-into-e-commerce-site-pages"></a>Integruj usługę Customer Voice ze stronami witryny handlu elektronicznego

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak zintegrować Microsoft Dynamics 365 Customer Voice ze stronami witryny e-commerce Dynamics 365 Commerce.

Możesz zintegrować [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) ze swoją witryną e-commerce, aby zbierać, analizować i śledzić opinie klientów w czasie rzeczywistym. Aby rozpocząć korzystanie z integracji, musisz utworzyć konto i wybrać szablon projektu Customer Voice dla typu informacji zwrotnej, którą chcesz zbierać.

## <a name="integrate-the-customer-voice-service"></a>Integracja usługi Customer Voice

Aby utworzyć konto odbiorcy w uowie, przejdź do usługi [Customer Voice](https://dynamics.microsoft.com/customer-voice/overview/) i postępuj zgodnie z monitami.

Po utworzeniu konta Customer Voice i zalogowaniu się, następnym krokiem jest wybranie szablonu projektu odpowiadającego rodzajowi informacji zwrotnej, którą chcesz zebrać.

Aby wybrać szablon projektu Customer Voice, wykonaj poniższe kroki.

1. Przejdź na stronę szablonu projektu [Customer Voice](https://customervoice.microsoft.com/Pages/ProjectPage.aspx).
1. Wybierz **Rozpocznij**.
1. Wybierz szablon projektu dla typu informacji zwrotnych, które chcesz gromadzić, a następnie wybierz przycisk **Dalej**.
1. W zakładce **Wyślij**, w sekcji **Wybierz format osadzenia**, wybierz format osadzenia. Pole **Kod osadzony** pokazuje kod, który musi być osadzony w projektancie stron Commerce.

Przykłady w tym artykule wykorzystują szablon projektu **Czasowe badanie opinii klientów** oraz format osadzenia **Przycisk**.

Poniższy przykład przedstawia stronę szablonu projektu **Czasowa ankieta dla klientów**, na której wybrano opcję osadzenia w formacie **Przycisk**, a kod osadzenia dla tej opcji pojawia się w polu **Kod osadzony**. Aby osadzić dostarczony kod na stronach twojej witryny, należy wykonać trzy osobne czynności, opisane w kolejnych sekcjach.

![Strona okresowej ankiety dla klientów programu Customer Voice z zaznaczoną opcją Przycisk.](media/customer-voice-integration-1.png)

### <a name="embed-the-external-script-url"></a>Osadź adres URL zewnętrznego skryptu

Na wszystkich stronach witryny, które powinny zawierać ankietę Customer Voice, musisz osadzić adres URL zewnętrznego skryptu, który Customer Voice podał w kodzie osadzania. Najlepszym sposobem na osadzenie skryptu na wielu stronach witryny jest utworzenie fragmentu w projektancie stron, który będzie zawierał adres URL zewnętrznego skryptu, a następnie dodanie tego fragmentu do odpowiednich szablonów stron. Po opublikowaniu zaktualizowanego szablonu osadzony kod skryptu zewnętrznego na stronach witryny, których to dotyczy, będzie przypominał poniższy przykład.

```html
<script src=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.js type="text/javascript"></script>
```

Aby uzyskać informacje na temat fragmentów, zobacz [Praca z fragmentami](work-with-fragments.md).

> [!NOTE]
> Musisz tylko dodać adres URL do fragmentu. Zewnętrzny moduł skryptowy doda inny kod skryptu.

Aby osadzić adres URL zewnętrznego skryptu we fragmencie, wykonaj poniższe kroki.

1. W programie do budowania witryn utwórz fragment oparty na module [Zewnętrzny moduł skryptu](script-module.md).
1. W nowym fragmencie zaznacz slot **Domyślny skrypt zewnętrzny**.
1. W okienku właściwości **Domyślny skrypt zewnętrzny**, w polu **Źródło skryptu** wpisz adres URL zewnętrznego skryptu, jak pokazano na poniższej ilustracji.

    ![Adres URL zewnętrznego skryptu w polu Źródło skryptu dla nowego fragmentu.](media/customer-voice-integration-2.png)

1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować fragment.

Nowy fragment, który zawiera osadzony blok zewnętrznego skryptu, jest teraz gotowy do dodania do odpowiedniego szablonu strony.

### <a name="embed-the-external-style-sheet-code"></a>Osadź kod zewnętrznego arkusza stylów

Następnie na wszystkich stronach witryny, które powinny zawierać ankietę Customer Voice, musisz osadzić zewnętrzny kod arkusza stylów, który Customer Voice udostępnił w kodzie osadzania. Podobnie jak w poprzedniej sekcji, najlepszym sposobem na osadzenie kodu zewnętrznego arkusza stylów na wielu stronach witryny jest utworzenie fragmentu w narzędziu budowania witryny, który zawiera kod arkusza stylów, a następnie dodanie tego fragmentu do odpowiednich szablonów stron. Kod osadzonego zewnętrznego arkusza stylów będzie przypominał poniższy przykładowy kod.

```typescript
<link rel="stylesheet" type="text/css" href=https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/Embed.css />
```

Aby osadzić kod zewnętrznego arkusza stylów we fragmencie, wykonaj poniższe kroki.

1. W programie do budowania witryn utwórz fragment oparty na module [Moduł metatagów](metatags-module.md).
1. We fragmencie zaznacz slot **Domyślne metatagi**.
1. W okienku właściwości **Domyślne metatagi**, w polu **Meta tagi** wpisz kod arkusza stylów, jak pokazano na poniższej ilustracji.

    ![Zewnętrzny kod arkusza stylów w polu Meta tagi dla nowego fragmentu.](media/customer-voice-integration-3.png)

1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować fragment.

Nowy fragment, który zawiera osadzony kod zewnętrznego arkusza stylów, jest teraz gotowy do dodania do odpowiedniego szablonu strony.

### <a name="embed-the-inline-script-code"></a>Osadzenie kodu skryptu wbudowanego 

Następnie na wszystkich stronach witryny, które powinny zawierać ankietę Customer Voice, musisz osadzić kod skryptu wbudowanego, który Customer Voice udostępnił w kodzie osadzonym. Podobnie jak w poprzednich rozdziałach, najlepszym sposobem na umieszczenie kodu skryptu wbudowanego na wielu stronach witryny jest utworzenie fragmentu w programie budującym witrynę, który będzie zawierał kod skryptu wbudowanego, a następnie dodanie tego fragmentu do odpowiednich szablonów stron.

W poniższym przykładzie kodu skryptu wbudowanego, **SURVEY\_KEY** jest znacznikiem miejsca. Wartość dla **SURVEY\_KEY** powinna odpowiadać faktycznemu kluczowi ankiety, który Customer Voice podał w kodzie osadzonym. Ostatnia linia wywołuje kod renderujący przycisk ankiety po jednej sekundzie, aby zapewnić skryptom wystarczającą ilość czasu na załadowanie się. W zależności od wybranej ankiety może być konieczne dodanie lub uaktualnienie innych metadanych, np. nazwy firmy.

```html
function renderSurveyButton() {
    var se = new SurveyEmbed("SURVEY_KEY","https://customervoice.microsoft.com/","https://mfpembedcdnmsit.azureedge.net/mfpembedcontmsit/","true");

    var context = {
        "First Name":"",
        "Last Name": "",
        "locale": "en-us",
        "companyname": "Adventure Works"
    };
    se.renderButton(context);
}

setTimeout(renderSurveyButton, 4000);
```

Aby osadzić kod skryptu wbudowanego we fragmencie, wykonaj poniższe kroki.

1. W programie do budowania witryn utwórz fragment oparty na module [Moduł skryptów wbudowanych](script-module.md).
1. W nowym fragmencie zaznacz slot **Domyślny skrypt wbudowany**.
1. W okienku właściwości **Domyślny skrypt wbudowany**, w polu **Skrypt wbudowany** wpisz kod skryptu wbudowanego, jak pokazano na poniższej ilustracji.

    ![Kod skryptu wbudowanego w polu wbudowanego skryptu dla nowego fragmentu.](media/customer-voice-integration-4.png)

1. Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.
1. Wybierz opcję **Publikuj**, aby opublikować fragment.

Nowy fragment, który zawiera osadzony kod skryptu wbudowanego, jest teraz gotowy do dodania do odpowiedniego szablonu strony.

## <a name="add-fragments-to-a-template"></a>Dodaj fragmenty do szablonu

Kiedy skończysz tworzyć fragmenty zawierające osadzony kod Customer Voice, musisz dodać je do szablonów stron powiązanych ze stronami witryny, na których chcesz ich używać. Na poniższej ilustracji trzy przykładowe fragmenty zostały dodane do szablonu strony ze szczegółami produktu (PDP).

![Przykładowe fragmenty dodane do szablonu PDP.](media/customer-voice-integration-5.png)

Po opublikowaniu zaktualizowanego szablonu ankieta "Customer Voice" pojawi się na wszystkich stronach, które są kontrolowane przez ten szablon.

Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z szablonami](work-with-templates.md).

## <a name="configure-content-security-policy"></a>Skonfiguruj politykę bezpieczeństwa treści

Domyślnie Content Security Policy (CSP) nie zezwala na połączenia z innymi usługami, chyba że zostanie przeprowadzona dodatkowa konfiguracja. Dlatego po opublikowaniu zaktualizowanych szablonów istnieje prawdopodobieństwo, że ankieta nie zostanie załadowana na odpowiednich stronach witryny. Aby zobaczyć błędy związane z CSP, otwórz narzędzia deweloperskie przeglądarki internetowej (F12), a następnie wejdź na stronę z ankietą. Błędy związane z CSP zostaną wyświetlone w konsoli.

Aby skonfigurować CSP w programie do budowania witryn i naprawić błędy, wykonaj poniższe kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. W zakładce **Polityka bezpieczeństwa treści** dodaj `https://customervoice.microsoft.com/` do dyrektywy **child-src**.
1. Dodaj `https://customervoice.microsoft.com/` do dyrektywy **frame-src**.
1. Dodaj `https://mfpembedcdnmsit.azureedge.net` i **.azureedge.net** do dyrektywy **img-src**.

Aby uzyskać więcej informacji, zajrzyj do [zasad zabezpieczeń dotyczących zawartości](manage-csp.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zewnętrzny moduł skryptowy](script-module.md)

[Moduł metatagów](metatags-module.md)

[Moduł skryptów wbudowanych](script-module.md)

[Polityka bezpieczeństwa treści](manage-csp.md)

[Praca z fragmentami](work-with-fragments.md)

[Praca z szablonami](work-with-templates.md)
