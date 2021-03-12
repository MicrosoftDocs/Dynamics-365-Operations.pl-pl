---
title: Dodawanie ikony favicon
description: W tym temacie opisano sposób dodawania ikony favicon do witryny.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: f249348fac526fc7814045b1b1b71c898430c0f2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980438"
---
# <a name="add-a-favicon"></a>Dodawanie ikony favicon

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób dodawania ikony favicon do witryny.

## <a name="overview"></a>Omówienie

Favicon jest małym plikiem graficznym wyświetlanym na karcie przeglądarki sieci Web, na pasku adresu, w historii przeglądania oraz w zakładkach lub ulubionych i w innych miejscach. Zaleca się dodanie favicon do witryny, ponieważ reprezentuje ona i wzmacnia daną markę oraz pomaga odróżnić witrynę od innych odwiedzanych przez odbiorców witryn sieci Web.

Chociaż do witryny można dodać wiele favicons różnych rozmiarów i typów plików, w tym temacie przedstawiono sposób dodawania jednego favicon. Jednak ten sam proces i lokalizacja są używane do dodawania kolejnych favicons.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Przekaż favicon do kolekcji składników majątku w witrynie

Aby przekazać favicon do kolekcji składników majątku w witrynie wykonaj procedurę opisaną w następujących krokach:

1. W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.
1. Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.
1. W oknie Eksploratora plików przejdź do pliku obrazu favicon, który chcesz przekazać, zaznacz go, a następnie wybierz pozycję **Otwórz**.
1. W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.
1. Jeśli chcesz opublikować obraz natychmiast po przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.

    > [!NOTE]
    > Jeśli nie zaznaczysz pola wyboru **Publikuj elementy multimedialne po przekazaniu**, musisz wrócić do strony **Elementy multimedialne** i ręcznie opublikować favicon później.

1. Kliknij przycisk **OK**.
1. W okienku właściwości po prawej stronie Skopiuj publiczny adres URL favicon. Ten adres URL będzie używany później.

## <a name="create-the-html-for-your-favicon"></a>Tworzenie kodu HTML dla pliku favicon

Aby utworzyć kod HTML dla pliku favicon, należy skorzystać z poniższego ciągu kodu HTML. W przypadku atrybutu **href** zamień wartość **Publiczny\_URL\_dla\_ikony\_favicon”** na skopiowany wcześniej, publiczny adres URL.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Tworzenie fragmentu zawierającego metatag dla ikony favicon

Aby utworzyć fragment zawierający metatag dla ikony favicon, wykonaj poniższe kroki.

1. Przejdź do obszaru **Fragmenty**, a następnie wybierz pozycję **Nowy**.
1. W oknie dialogowym **Nowy fragment** wybierz pozycję **Tagi meta** jako moduł, na którym oparty jest fragment strony.
1. Wprowadź nazwę fragmentu, a następnie kliknij przycisk **OK**.
1. W drzewie hierarchii fragmentów wybierz element podrzędny **Domyślne tagi meta**.
1. W prawym okienku, w obszarze **Tagi meta**, wybierz pozycję **Dodaj**, a następnie wprowadź ciąg HTML utworzony wcześniej dla ikony favicon. 
1. Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować fragment.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>Dodawanie fragmentu metatagów do sekcji nagłówka kodu HTML stron

Aby dodać fragment metatagów do sekcji **nagłówka** kodu HTML stron, wykonaj następujące kroki.

1. Przejdź do obszaru **Szablony**, otwórz szablon stron, do których chcesz dodać ikonę favicon, a następnie wybierz pozycję **Edytuj**.
1. W drzewie hierarchii szablonów wybierz przycisk wielokropka (**...**) znajdujący się po prawej stronie kontenera **nagłówek HTML**, a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Wybieranie fragmentu** wybierz utworzony wcześniej fragment metatagów, a następnie kliknij przycisk **OK**.
1. Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.

> [!NOTE]
> Jeśli witryna używa więcej niż jednego szablonu, musisz dodać fragment metatagów do wszystkich tych szablonów.

Podczas wyświetlania podglądu stron opartych na szablonie, do którego dodano fragment metatagów, ikona favicon powinna być teraz widoczna na karcie przeglądarki.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie logo](add-logo.md)

[Wybór motywu witryny](select-site-theme.md)

[Praca z plikami zastępowania CSS](css-override-files.md)

[Dodawanie wiadomości powitalnej](add-welcome-message.md)

[Dodawanie powiadomienia o prawach autorskich](add-copyright-notice.md)

[Dodawanie języków do witryny](add-languages-to-site.md)

[Dodawanie kodu skryptu do stron witryny w celu obsługi telemetrii](add-telemetry.md)

