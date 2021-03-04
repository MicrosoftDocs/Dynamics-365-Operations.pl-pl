---
title: Podwyższanie poziomu odmiany i kończenie eksperymentu
description: W tym temacie opisano sposób podnoszenia poziomu udanej odmiany i zakończenia eksperymentu w systemie Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c7da601323663d4c1ea76f7cad7bdab8e7632d1c
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "4415084"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Podwyższanie poziomu odmiany i kończenie eksperymentu

W tym temacie opisano sposób podnoszenia poziomu odmian, które wywołały najlepsze wyniki w eksperymencie, oraz sposobu zakończenia eksperymentu. Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych tematach.

[ ![Proces użytkownika eksperymentu — przegląd i zakończenie](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Po [wykonaniu eksperymentu](experimentation-run-monitor.md) i zebraniu odpowiednich danych w celu ustalenia, które odmiany mają być używane w działającej witrynie można podwyższyć poziom odmiany i zakończyć eksperyment.

## <a name="promote-a-variation"></a>Podwyższanie poziomu odmiany
Użyj danych i analiz związanych z eksperymentem w usłudze innej firmy w celu określenia, które odmiany dają najlepsze wyniki. Następnie możesz ją promować, zamieniając bieżącą zawartość w działającej witrynie na zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej.

Aby promować wygrywającą odmianę, wykonaj następujące kroki. 

1. W konstruktorze witryn Commerce wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie.
1. Na pasku poleceń wybierz **Zakończ eksperyment**.
1. W oknie dialogowym **Zakończ eksperyment** wybierz opcję **Zrecenzuj dane eksperymentu**. Otwiera się usługa innej firmy otwiera się, można sprawdzić poprawność metryk i określić, które odmiany były najskuteczniejsze.
1. W okienku dialogowym **Zakończ eksperyment** wybierz zwycięską odmianę, a następnie wybierz przycisk **Dalej**.
1. Otwórz usługę innej firmy i zatrzymaj eksperyment.
1. W konstruktorze witryn wybierz opcję **Zakończ**, aby zastąpić oryginalną działającą stronę i opublikować zwycięską odmianę, tak aby była dostępna dla wszystkich użytkowników witryny internetowej. 

> [!NOTE]
> Jeśli zostanie wybrana opcja zachowania bieżącej działające strony i nie zostanie opublikowana odmiana, wybierz opcję **Ponownie opublikuj oryginalną stronę**.

## <a name="delete-your-experiment"></a>Usuwanie eksperymentu
Jeśli nie jest wymagane usuwanie ukończonego eksperymentu w systemie Commerce, można go usunąć, aby zaoszczędzić miejsce lub oczyścić obszar roboczy. 

Aby usunąć eksperyment w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie. 
    > [!NOTE]
    > Jeśli eksperyment jest nadal aktywny, przed kontynuowaniem zatrzymaj eksperyment w usłudze innej firmy.
1. Wybierz opcję **Cofnij publikowanie** na pasku poleceń, aby usunąć zawartość odmiany z działającej witryny.
1. Wybierz przycisk **Usuń**, aby usunąć eksperyment.

## <a name="previous-step"></a>Poprzedni krok
[Uruchamianie i monitorowanie eksperymentu](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]