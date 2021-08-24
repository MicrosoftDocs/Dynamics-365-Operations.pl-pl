---
title: Konfigurowanie firmy zależnej do konsolidacji
description: W tym temacie opisano sposób pracy z wykresami kont dla konsolidowanej firmy.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: fbec5ad8fa5e17b75859c07ee64a66c9568c97d3d18b6a7616a64303d3a33f10
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727966"
---
# <a name="set-up-a-subsidiary-legal-entity-for-consolidation"></a>Konfigurowanie firmy zależnej do konsolidacji

[!include [banner](../includes/banner.md)]

Metoda przygotowywania kont oddziałów do konsolidacji zależy w części od tego, w jakim zakresie struktura planu kont w firmie zależnej odzwierciedla plan kont w konsolidowanej firmie.

Przed rozpoczęciem konsolidacji w ramach zamknięcia okresu należy przeprowadzić czynności wstępne przy zamykaniu okresu, ale nie należy zamykać kont oddziałów przed zakończeniem konsolidacji. Aby uzyskać więcej informacji na temat zamknięcia na koniec okresu, zobacz [Zamknięcie księgi głównej na koniec okresu](close-general-ledger-at-period-end.md) i [Zamykanie roku obrachunkowego](tasks/close-fiscal-year.md).

> [!NOTE]
>  Zalecamy użycie narzędzia Management Reporter dla Microsoft Dynamics 365 Finance w celu połączenia wyników finansowych wielu firm w skonsolidowanym formacie. Program Management Reporter umożliwia tworzenie skonsolidowanych raportów finansowych dla różnych firm, używanie programu Excel do importowania danych konsolidacji z innych źródeł oraz przetłumaczenie kwot na dowolną liczbę walut raportowania bez konieczności uruchamiania procesu konsolidacji w Dynamics 365 Finance.

## <a name="map-subsidiary-main-accounts-to-consolidated-main-accounts"></a>Odwzorowanie kont głównych na konsolidowane konta główne

Jeśli plan kont w firmie zależnej nie odzwierciedla planu kont w konsolidowanej firmie, można zmapować konta główne w firmie zależnej na konta główne w firmie konsolidowanej.

1. W *zależna osoba prawna* przejdź do **Księga główna \> Konfiguracja** \> **Plan kont \> Plan kont**.
2. Wybierz plan kont. Na skróconej karcie **Konta główne** wybierz konto główne, a następnie wybierz pozycję **Edytuj**.
3. Wybierz konto główne firmy zależnej, które musi być mapowane na konsolidowane konto główne. Na skróconej karcie **Ogólne** w polu **Konto konsolidacji** wprowadź konto w konsolidowanej firmie, na które musi zostać przeniesione saldo lub transakcje z wybranego konta głównego jednostki zależnej. To samo konto główne konsolidowane można wprowadzić dla kilku kont zależnych.

    > [!NOTE]
    > Jeśli typy mapowanych kont głównych zależnych różnią się od typu kont głównych w firmie konsolidowanej, wartości konta, których typem konta głównego jest **Suma** są zastępowane podczas konsolidacji.

4. Przygotowywanie raportów i sprawozdań finansowych dla firmy skonsolidowanej opartych na wymiarach finansowych. Aby zamapować wymiary finansowe używane na kontach oddziałów na wymiary finansowe w skonsolidowanej firmie:

    1. W *zależna osoba prawna*, go to **Księga ogólna \> Konfiguracja \> Wymiary finansowe \> Wymiary finansowe**, wybierz wymiar finansowy, a następnie wybierz wartości wymiaru finansowego i wybierz **Wartości wymiarów finansowych**.
    2. Wybierz wartość wymiaru finansowego do mapowania na inną wartość wymiaru finansowego w firmie konsolidowanej.
    3. Na skróconej karcie **Ogólne** w polu **Wymiar grupy** wprowadź wymiar finansowy w firmie konsolidowanej. Podczas konsolidacji ten wymiar finansowy będzie przypisywany do transakcji i sald, które używają wybranego wymiaru finansowego w firmie zależnej. Wymiary finansowe wprowadzone w tym miejscu muszą być użyte w firmie konsolidowanej. Można przypisać wymiar finansowego, który jest używany jako grupa wymiarów finansowych do kilku wymiarów finansowych zależnych.

5. Jeśli przeprowadzasz konsolidację online, wykonaj następujące kroki, aby upewnić się, że transfery przebiegają zgodnie z zamierzeniami:

    1. W *firmie skonsolidowanej* przejdź do **Księga główna \> Okresowe \> Konsolidowanie \> Konsolidowanie \[Eksportuj do\]**, aby otworzyć stronę **Konsolidowanie \[Online\]**.
    2. Na karcie **Kryterium** zaznacz pole wyboru **Użyj konta konsolidacji**.
    3. Na karcie **Wymiary finansowe** wybierz odpowiednie wymiary finansowe.
    4. Dla każdego wybranego wymiaru finansowego wprowadź liczbę w polu **Zamówienie na segment**, aby wskazać kolejność, w jakiej powinny się pojawiać wymiary.

## <a name="maintain-the-same-chart-of-accounts-in-the-subsidiary-and-consolidated-legal-entities"></a>Zachowaj ten sam plan kont w firmie zależnej i firmie konsolidowanej

Konta główne w firmie zależnej mogę mieć te same numery kont i tę samą strukturę planu kont jak konta główne w firmie konsolidowanej. W tym przypadku nie trzeba ręcznie mapować kont głównych w firmie zależnej na konta główne w firmie konsolidowanej.

Przed rozpoczęciem konsolidacji wykonaj następujące czynności.

1. W *firmie skonsolidowanej* przejdź do **Księga główna \> Okresowe \> Konsolidowanie \> Konsolidowanie \[Eksportuj do\]**, aby otworzyć stronę **Konsolidowanie \[Online\]**.
2. Zaznacz pole wyboru **Użyj konta konsolidacji**. Podczas konsolidacji transakcje i salda będą automatycznie przenoszone na właściwe konta.

> [!NOTE]
> Jeśli konta nie są zgodne, konsolidacja zostanie zatrzymana i zostanie wyświetlony komunikat.

## <a name="create-a-chart-of-accounts-for-the-consolidated-legal-entity-based-on-an-existing-chart-of-accounts"></a>Tworzenie planu kont dla firmy konsolidowanej na podstawie istniejących planów kont

Konsolidację można przeprowadzić, nawet jeśli plan kont nie został jeszcze utworzony w firmie podlegającej konsolidacji.

- Jeśli zaplanowałeś strukturę kont, której chcesz użyć w firmie objętej konsolidacją, możesz zamapować konta zależne na tę strukturę.
- Jeśli nie dokonano mapowania kont firmy zależnej, konta konsolidowanej firmy zostaną automatycznie utworzone podczas transferowania danych firmy zależnej do konsolidowanej firmy. Te konta są oparte na koncie głównym. Kolejne dane są akumulowane na kontach w firmie konsolidowanej, które mają ten sam numer konta jak konta firmy zależnej.

Bez względu na to, czy wykonano mapowanie kont, czy nie, przed rozpoczęciem tego rodzaju konsolidacji należy usunąć zaznaczenie pola wyboru **Użyj konta konsolidacji** na stronie **Konsolidowanie** dla konsolidowanej firmy.

> [!NOTE]
> Przy użyciu tej metody można utworzyć plan kont konsolidowanej firmy na podstawie planu kont jednej z firm zależnych. (Aby uzyskać więcej informacji, zobacz temat [Grupy kont konsolidacji i dodatkowe konta konsolidacji](../budgeting/consolidation-account-groups-consolidation-accounts.md).) Następnie przypisz odpowiednią zasadę konwersji konsolidacji do każdego skonsolidowanego konta głównego i uruchom konsolidację dla wszystkich firm oddziału.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]