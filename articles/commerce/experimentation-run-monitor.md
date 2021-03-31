---
title: Uruchamianie i monitorowanie eksperymentu
description: W tym temacie opisano sposób uruchamiania i monitorowania eksperymentów w usłudze innej firmy. Opisano w nim także sposób wprowadzania zmian w odmianach po rozpoczęciu eksperymentu.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 956a9168ed7bf9282d9eeec39587d8e1f2d1856c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224889"
---
# <a name="run-and-monitor-an-experiment"></a>Uruchamianie i monitorowanie eksperymentu

W tym temacie opisano sposób uruchamiania i monitorowania eksperymentów w aplikacji innej firmy oraz zmiany odmian w razie potrzeby. Przed wykonaniem kroków opisanych w tym temacie najpierw należy [opublikować](experimentation-preview-publish.md) eksperyment w Commerce. 

Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych tematach.

[ ![Proces użytkownika eksperymentu — uruchamianie i monitorowanie](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

Po opublikowaniu odmian należy wykonać wszystkie kroki niezbędne do wykonania eksperymentu w Commerce. Następnym krokiem jest określenie, które odmiany mają być pokazywane każdemu użytkownikowi, gdy zażądają strony. Usługa innej firmy wymusza to określenie, ale najpierw należy aktywować eksperyment w usłudze. Ponieważ czynności wykonywane w celu aktywowania eksperymentu różnią się w zależności od usługi, należy wykonać instrukcje dostępne w usłudze lub uzyskane od dostawcy. Jeśli eksperyment nie zostanie aktywowany, użytkownicy będą widzieć wersję domyślną strony (nie będą wyświetlane odmiany).

Aby zebrać dane na temat wyników prawidłowych statystycznie, czasu trwania eksperymentu musi być wystarczający. Usługa innej firmy umożliwia monitorowanie danych i analiz związanych z eksperymentem podczas wykonywania eksperymentu.

## <a name="adjust-your-variations"></a>Korygowanie odmian
Jeśli z dowolnej przyczyny konieczna jest modyfikacja odmiany, należy wykonać poniższe kroki.

> [!IMPORTANT]
> Jeśli wprowadzisz zmiany w działającym eksperymencie w Commerce lub usłudze innej firmy, może to znacząco wpłynąć na wyniki. Rozważ możliwość przeprowadzenia eksperymentu, a następnie utworzenia nowego eksperymentu dotyczącego istotnych zmian.

1. W konstruktorze witryn Commerce wybierz **Eksperymenty** w lewym okienku nawigacji, a następnie wybierz doświadczenie. 
1. Z menu rozwijanego wybierz odmiany, które mają zostać zaktualizowane.
1. Wprowadź wszystkie wymagane zmiany, a następnie wyświetl podgląd i opublikuj odmiany. Aby uzyskać więcej informacji, zobacz temat [Podgląd i publikowanie eksperymentu](experimentation-preview-publish.md).
1. Przejdź do usługi innej firmy, aby dokonywać wszelkich zmian związanych z konfiguracją eksperymentu.
    
## <a name="previous-step"></a>Poprzedni krok
[Podgląd i publikowanie eksperymentu](experimentation-preview-publish.md)

## <a name="next-step"></a>Następne kroki
[Podwyższanie poziomu odmiany i kończenie eksperymentu](experimentation-review-complete.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]