---
title: Zestawy wymiarów finansowych
description: W tym artykule opisano zestawy wymiarów finansowych i przedstawiono kilka wskazówek dotyczących optymalizacji ich użycia.
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 3d4c15504b2ad128493e1bafa36aed271c2ab6dc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864289"
---
# <a name="financial-dimension-sets"></a>Zestawy wymiarów finansowych

[!include [banner](../includes/banner.md)]

W tym artykule opisano zestawy wymiarów finansowych i przedstawiono kilka wskazówek dotyczących optymalizacji ich użycia.

Zestaw wymiarów to uporządkowana lista wymiarów finansowych, której można użyć do podsumowania danych księgi głównej w sposób zdefiniowany przez użytkownika. Podstawowym zastosowaniem zestawów wymiarów jest zdefiniowanie salda próbnego.

Jedynym standardowym zestawem wymiarów jest zestaw wymiarów, który zawiera tylko konto główne.

Strona **Zestawy wymiarów finansowych** służy do tworzenia zestawów wymiarów finansowych i zarządzania nimi.

## <a name="dimension-set-balances"></a>Salda zestawów wymiarów

Zestaw wymiarów może mieć salda oparte na jego wymiarach finansowych. Salda istnieją w księdze głównej i są oparte na definicji zestawu wymiarów. Salda są sumowane na podstawie danych księgi głównej, aby poprawić wydajność podczas ich pobierania (na przykład podczas generowania salda próbnego).

## <a name="create-balances"></a>Utwórz salda

Przycisk **Utwórz salda** służy do inicjowania sald dla zestawu wymiarów, który obecnie nie ma sald.

> [!NOTE]
> Zaleca się ograniczenie liczby zestawów wymiarów, które mają salda, ponieważ aktualizacje salda mają wpływ na wszystkie działania księgowania księgi głównej.

## <a name="update-balances"></a>Aktualizuj salda

Użyj przycisku **Aktualizuj salda**, aby uwzględnić w saldach najnowsze działanie księgowania księgi głównej. Aktualizacje salda są lekkimi operacjami. Muszą przetwarzać tylko działanie księgowania księgi głównej, które wystąpiło od ostatniej aktualizacji.

> [!NOTE]
> Wyświetlenie salda próbnego wymusza aktualizację, aby upewnić się, że pokazywane salda są aktualne. Rozważ użycie cyklicznego zadania wsadowego, aby aktualizacje najczęściej używanych zestawów wymiarów były szybkie. W ten sposób pomagasz zminimalizować czas, jaki muszą czekać użytkownicy salda próbnego.

## <a name="rebuild-balances"></a>Odbuduj salda

Przycisk **Odbuduj salda** umożliwia ponowne tworzenie sald od podstaw. W ten sposób można zapewnić, że są one zgodne z danymi w księdze głównej. Przebudowa sald wymaga dużo przetwarzania i zwykle nie powinna być wymagana.

> [!NOTE]
> Jeśli masz scenariusz, który regularnie wymaga przebudowy sald, zaleca się skontaktować się z obsługą klienta. Obsługa klienta może pomóc w określeniu, dlaczego salda nie są zgodne z danymi w księdze głównej.

## <a name="clear-balances"></a>Uzgodnij salda

Użyj przycisku **Wyczyść salda**, aby usunąć salda i zatrzymać dalsze aktualizacje. Zestaw wymiarów nie będzie już miał wpływu na działania księgowania księgi głównej.

## <a name="delete-a-dimension-set"></a>Usuwanie zestawu wymiarów

Nie **usuwaj i nie twórz ponownie** zestawów wymiarów jako żadnej formy obejścia potencjalnych problemów z danymi salda dla określonego zestawu wymiarów. Odtworzenie zestawu wymiarów jest kosztowne. Aby uzyskać dalszą pomoc w przypadku problemów, skontaktuj się z obsługą klienta. 


Aby uzyskać więcej informacji, zobacz [Wymiary finansowe](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
