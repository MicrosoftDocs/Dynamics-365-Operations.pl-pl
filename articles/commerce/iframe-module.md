---
title: Moduł iframe
description: W tym temacie opisano moduł iframe i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: eeb9d76367be6b2d2153578f6358594b807382ac
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780241"
---
# <a name="iframe-module"></a>Moduł iframe

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł iframe i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł iframe udostępnia element iframe (ramkę wbudowaną), który obsługuje zawartość zewnętrzną w witrynie. Na przykład można go używać do obsługi pliku wideo YouTube lub przeglądarki plików PDF na dowolnej stronie witryny. 

Moduł iframe wymaga docelowego adresu URL. Następnie znajduje zawartość strony docelowej w elemencie **iframe** HTML. Zewnętrzne adresy URL muszą znajdować się na liście dozwolonych zgodnie z zasadami zabezpieczeń zawartości (CSP) witryny. W przypadku zawartości iframe adresy URL powinny być dozwolone przy użyciu dyrektywy **przodek ramki**. Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md).

> [!NOTE]
> Moduł iframe jest dostępny w wydaniu Dynamics 365 Commerce 10.0.13.

Poniższy obraz przedstawia przykłady modułów iframe, które prezentują zewnętrzne pliki wideo na stronach witryny.

![Przykład modułów iframe, które prezentują zewnętrzne pliki wideo.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Właściwości modułu Iframe

| Nazwa właściwości             | Wartość                 | opis |
|---------------------------|-----------------------|-------------|
| Nagłówek | Tekst | Nagłówek modułu. |
| Docelowy adres URL | Adres URL | Adres URL znajdujący się w module. |
| Wysokość | Liczba lub procent | Wysokość modułu w pikselach lub w procentach. Na przykład wartość **100** będzie traktowana jako liczba pikseli, a wartość **100%** będzie traktowana jako wartość procentowa. |
| Etykieta aria | Tekst | W celu ułatwienia dostępu można zdefiniować etykietę Accessible Rich Internet Applications (ARIA). |

## <a name="add-an-iframe-module-to-a-page"></a>Dodawanie modułu iframe do strony

Aby dodać moduł iframe do strony w celu wyświetlenia zewnętrznego wideo, należy wykonać następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon marketingowy**, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź **Strona marketingowa**, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz szablon** wybierz **szablon marketingowy**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz układ strony (na przykład **Układ elastyczny**), a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**. 
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduły** wybierz moduł **iframe** i wybierz przycisk **OK**.
1. W okienku właściwości modułu należy określić wartość **Docelowego adresu URL** w celu uzyskania zewnętrznego adresu URL wideo.
1. W razie konieczności określ inne właściwości, takie jak **Nagłówek** i **Wysokość**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do strony Marketing w witrynie. Należy sprawdzić, czy plik wideo jest renderowany w module iframe.

> [!NOTE]
> Ponieważ moduł iframe zawiera zawartość zewnętrzną, twórcy witryny muszą zagwarantować, że zawartość hostowana w module iframe nie będzie naruszać zasad ograniczeń dotyczących zawartości na odpowiednim rynku. Jeśli na stronie korzystającej z modułu iframe doszło do naruszenia zawartości, autor witryny może usunąć moduł iframe, otwierając stronę w Konstruktorze witryn, wybierając opcję **Usuń moduł** w gnieździe modułu iframe, a następnie zapisując i ponownie opublikować stronę.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Zarządzanie zasadami zabezpieczeń zawartości (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
