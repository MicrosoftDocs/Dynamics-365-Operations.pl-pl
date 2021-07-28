---
title: Moduł Subskrybuj
description: W tym temacie opisano moduły subskrypcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e70bc01d4c662d08a9171a9d2feb0e2f7901ccbb
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479522"
---
# <a name="subscribe-module"></a>Moduł Subskrybuj

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano moduły subskrypcji i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduły subskrypcji mogą być używane na stronach witryny w celu przechwytywania informacji o klientach do biuletynów lub promocji.

Poniższa ilustracja przedstawia przykład modułu subskrypcji w stopce strony witryny Adventure Works.

![Przykład modułu subskrypcji w stopce strony witryny Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - Moduł subskrypcji jest dostępny w bibliotece modułów Commerce od wydania Dynamics 365 Commerce w wersji 10.0.20.
> - Moduł subskrypcji jest prezentowany w temacie Adventure Works.
> - Moduł subskrypcji wymaga rozszerzenia akcji danych do pracy z niektórymi dostawcami marketingowych wiadomości e-mail, dzięki czemu biuletyn lub promocyjne wiadomości e-mail mogą być wysyłane po przechwyceniu informacji o kliencie.

## <a name="subscribe-module-properties"></a>Właściwości modułu Subskrybowanie

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Nagłówek tekstowy modułu subskrypcji, np. **Subskrybowanie biuletynu** lub **Zarejestruj się, aby otrzymać 10% rabatu**. |
| Akapit     | Tekst akapitu | Moduł subskrypcji obsługuje tekst akapitowy w formacie bogatego tekstu, aby zapewnić dodatkowe szczegóły dla wezwania do działania w nagłówku. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Dodaj moduł subskrypcji do nowej strony

Aby dodać moduł listy subskrypcyjnej do nowej strony i ustawić wymagane właściwości w kreatorze stron Commerce, wykonaj poniższe kroki.

1. Przejdź do formularza **Szablony** i otwórz szablon marketingowy dla strony głównej witryny (lub utwórz nowy szablon marketingowy).
1. W gnieździe **Głównym** na stronie domyślna wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Subskrypcja** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do formularza **Strony** i otwórz stronę główną witryny (lub utwórz nową stronę główną, używając szablonu marketingowego).
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Subskrypcja** i wybierz przycisk **OK**.
1. W okienku właściwości modułu subskrybowania dodaj nagłówek, na przykład **Subskrybuj**.
1. Dodaj tekst akapitu, np. **Najnowsze trendy, style i promocje. Jesteś na liście? Zapisz się i otrzymuj najnowsze gorące oferty!**
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Motyw Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
