---
title: Tworzenie adresu URL strony
description: W tym temacie przedstawiono podstawowe pojęcia i procedury dotyczące tworzenia adresu URL strony w witrynie.
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8e221bd975fd984379724b751f6c026acfda7b07
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207902"
---
# <a name="create-a-page-url"></a>Tworzenie adresu URL strony


[!include [banner](includes/banner.md)]

W tym temacie przedstawiono podstawowe pojęcia i procedury dotyczące tworzenia adresu URL strony w witrynie.

## <a name="overview"></a>Omówienie

Pełny lub bezwzględny adres URL wskazujący stronę w witrynie składa się z różnych części. Adres URL `https://www.contoso.com/en-us/contactus` zawiera na przykład następujące elementy:

- `https://www.contoso.com` — Protokół HTTP i domenę witryny.
- `/en-us` — Ścieżka języka witryny.
- `/contactus`— Względny adres URL strony **Skontaktuj się z nami**. Względny adres URL jest również znany jako *URL*.

Podczas konfigurowania witryny użytkownik określa domenę serwisu i opcjonalną ścieżkę języka. Za pośrednictwem strony sklepy internetowe w ustawieniach witryny można dodawać kolejne domeny i ścieżki językowe do witryny.

URL strony istnieje jako jednostka samodzielna w środowisku tworzenia witryn. URL strony składa się z dwóch części: nazwy reprezentującej adres URL, a także wskaźnika do strony w witrynie lub zewnętrznej witrynie URL strony można również skonfigurować w taki sposób, aby pełnił rolę przekierowania do innej strony w oddziale lub witrynie zewnętrznej.

## <a name="create-a-page-url"></a>Tworzenie adresu URL strony

Adresy URL stron można tworzyć na dwa sposoby:

- Automatycznie podczas tworzenia strony
- Ręcznie, ze strony adresy **URL**

### <a name="create-a-page-url-when-you-create-a-page"></a>Utwórz adres URL strony podczas tworzenia strony

Jeśli podczas tworzenia nowej strony w polu adresu **URL** zostanie wprowadzona nazwa, adres URL strony wskazujący na tę stronę zostanie automatycznie utworzony na stronie adresy **URL**. Po opublikowaniu adresu URL i strony wskazywanej przez użytkownika, użytkownicy witryny (odbiorcy) mogą uzyskać dostęp do strony skojarzonej z adresem URL.

> [!NOTE]
> Jeśli publikujesz adres URL bez publikowania strony, do której on wskazuje, użytkownicy witryny otrzymają komunikat o błędzie 404 przy próbie uzyskania dostępu do strony. Jeśli strona zostanie opublikowana bez publikowania adresu URL, który wskazuje na Tę stronę, nie można uzyskać dostępu do tej strony przy użyciu adresu URL.

### <a name="manually-create-a-page-url"></a>Ręczne tworzenie adresu URL strony

Podczas tworzenia nowych stron nie jest wymagane określanie adresu URL strony. Jeśli pole adresu URL pozostanie puste, Strona zostanie utworzona w stanie niepołączonym. W takim przypadku klienci nie będą mogli uzyskać dostępu do strony, nawet jeśli jest ona opublikowana. Aby udostępnić stronę, musisz ręcznie utworzyć adres URL i połączyć go z tą stroną.

Aby ręcznie utworzyć adres URL strony, należy wykonać następujące kroki.

1. Na stronie **adresy URL** wybierz opcję **Nowe**.
1. Wybierz stronę witryny, aby powiązać ją z adresem URL.
1. Wprowadź URL, a następnie kliknij przycisk **OK**.

W tym momencie adres URL jest w stanie wersji roboczej. Aby użytkownicy witryny mogli uzyskać dostęp do skojarzonej strony, musi zostać opublikowana.

## <a name="update-a-page-url"></a>Aktualizacja adresu URL strony

Aby zaktualizować stronę docelową adresu URL strony, wykonaj następujące kroki.

1. Na stronie adresy **URL** wybierz adres URL, który ma zostać zaktualizowany.
1. W okienku właściwości po prawej stronie wybierz przycisk wielokropka (**...**) obok pola strony docelowej.
1. W oknie dialogowym wybierz inną stroną i wybierz przycisk **OK**.
1. Zapisz i opublikuj URL.

## <a name="redirect-a-page-url"></a>Przekieruj stronę URL

Czasami klienci mogą wyświetlać inną stronę, gdy żądają określonego adresu URL. W takich przypadkach najlepszym i najprostszym sposobem jest często zmiana strony, na którą wskazuje adres URL strony. Mogą jednak istnieć uzasadnione przyczyny użycia protokołu HTTP 301 lub 3023 przekierowywania do przekierowywania żądań o adres URL do innego adresu URL.

Aby przekierować adres URL do innego adresu URL, wykonaj następujące kroki.

1. Na stronie adresy **URL** wybierz adres URL, który ma zostać zaktualizowany.
1. W okienku właściwości po prawej stronie wybierz opcję **Przekieruj**.
1. Wybierz cel dla przekierowania.

    - Aby wskazać inną stronę w witrynie, wybierz opcję **wewnętrzny adres URL**, a następnie wybierz przycisk wielokropka (**...**), a następnie wybierz adres URL do przekierowania.
    - Aby wskazać stronę w witrynie zewnętrznej, wybierz **zewnętrzny adres URL**, a następnie wprowadź pełny adres URL tej strony. Pamiętaj, aby uwzględnić protokół. Na przykład wpisz `https://domain.com/new/page`. Jeśli adres URL już przekierowuje do wewnętrznego adresu URL, należy zaznaczyć pole wyboru **Wyczyść zaznaczenie**, aby można było wprowadzić zewnętrzny adres URL.

1. Wybór typu przekierowania:

    - **Stałe przekierowanie (301)** — tę opcję należy wybrać, jeśli wiadomo, że zawartość jest trwale przenoszona i nie zostanie przywrócona do poprzedniego adresu URL. Aparaty wyszukiwania będą przypisywać wartość adresu URL funkcji optymalizacji aparatu wyszukiwania (SEO) do adresu URL, na który jest przekierowywany i aktualizuje rekord w celu wyświetlenia nowego adresu URL. 
    - **Tymczasowe przekierowanie (302)** — tę opcję należy wybrać, aby przekierować ruch bez aktualizowania aparatów wyszukiwania. Ta metoda jest zazwyczaj używana, gdy zawartość zostanie wkrótce przywrócona do poprzedniego adresu URL.

1. Po przygotowaniu się do zaimplementowania przekierowania zapisz i opublikuj adres URL.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dostosowywanie nawigacji w witrynie](customize-site-navigation.md)

[Dodawanie nowej strony witryny](add-new-page.md)

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Dodawanie języków do witryny](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]