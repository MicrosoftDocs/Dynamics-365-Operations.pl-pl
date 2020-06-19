---
title: Utwórz i zastosuj warunki zatrzymania płatności u dostawcy
description: Ten temat zawiera informacje dotyczące konfigurowania i obsługiwania warunków zatrzymania płatności dostawcy.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410257"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Utwórz i zastosuj warunki zatrzymania płatności u dostawcy

[!include [banner](../includes/banner.md)] 

Ustawienie warunków zatrzymania płatności dla dostawcy dla projektu jest przydatne, gdy organizacja chce zachować część płatności dokonanych dla dostawcy. Na przykład, jeśli chcesz wstrzymać płatność do dostawcy, dopóki dostarczone produkty nie spełnią oczekiwań użytkownika. Warunki zatrzymania płatności dostawcy można określić podczas negocjacji umowy z dostawcą.

## <a name="create-vendor-payment-retention-terms"></a>Utwórz warunki zatrzymania płatności dostawcy

Można wprowadzić procent płatności dla dostawcy, jaki ma być zatrzymany oraz procent poprzednio zatrzymanych kwot, jakie mają być zwolnione. Stosowne kwoty zostają automatycznie zatrzymane na fakturach dostawcy, dopóki umowa nie zostanie wykonana w stopniu określonym w umowie. Po skonfigurowaniu warunków przechowywania możesz je zastosować w dowolnym projekcie dla tego dostawcy.

Należy wykonać następujące kroki, aby skonfigurować i obsługiwać warunki zatrzymania płatności dla dostawcy. 

1. Przejdź do **Zarządzanie projektami i ich księgowanie** > **Zatrzymanie** > **Warunki zatrzymania płatności u dostawcy**.
2. Wybierz **Nowy**, aby dodać nowy warunek zatrzymania płatności dla dostawcy. Wartość stanowiąca **Identyfikator reguły** dla nowego warunku zostanie wprowadzona automatycznie. 
3. Wprowadź krótki opis w polu **Opis**, a następnie na skróconej karcie **Warunki** wybierz opcję **Dodaj wiersz**, aby wprowadzić wartości warunków dla następujących:

   - **Procent dostarczonych jednostek**: Wprowadź procent ukończenia dla warunku. Stosowne kwoty zostają automatycznie zatrzymane na fakturach od dostawcy do czasu ukończenia etapu projektu odpowiadającego określonej wartości procentowej. Na przykład, jeśli wprowadzi się wartość 50.00, kwoty zostaną zatrzymywane dopóty, dopóki projekt nie zostanie ukończony w 50 procentach.
   - **Procent do zatrzymania**: Wprowadź procent kwoty z faktury dostawcy, jaki ma być zatrzymany. Na przykład, jeśli zostanie wprowadzona wartość 10,00, to zatrzymywaniu będzie podlegało 10 procent kwoty na fakturze od dostawcy do momentu, gdy projekt nie osiągnie etapu ukończenia określonego w polu **Procent dostarczonych jednostek**.
   - **Procent do zwolnienia**: Wybierz **Dodaj wiersz** i wprowadź procent jakichkolwiek wcześniej zatrzymanych kwot, jaki ma być zwolniony po osiągnięciu określonego poziomu ukończenia projektu.

> [!NOTE]
> Jeśli projekt obejmuje więcej niż jeden kamień milowy dla różnych poziomów ukończenie projektu, wprowadź osobny wiersz warunku zatrzymania płatności dla dostawcy dla każdej reguły zatrzymania. Każdy wiersz może określać inną wartość procentową zatrzymania i inny procent do zwolnienia dla każdego wyznaczonego poziomu ukończenia projektu.

Po utworzeniu warunków zatrzymania dostawcy dla dostawcy można zastosować warunki do projektu.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Zastosuj warunki zatrzymania dostawcy do projektu

1. Przejdź do **Zarządzanie projektami i ich księgowanie** > **Projekty** > **Wszystkie projekty**, a następnie otwórz projekt ze strony Lista projektów.
2. Na skróconej karcie **Umowy z dostawcami**, wybierz **Dodaj wiersz**.
3. W **polu Kod konta** wybierz jedną z następujących opcji: 

   - **Tabela**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do jednego dostawcy.
   - **Grupa**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do wszystkich dostawców w wybranej grupie dostawców.
   - **Wszystko**: Warunki zatrzymania płatności dla dostawcy mają zastosowanie do wszystkich dostawców.

4. W **polu Dostawca/grupa dostawców** wybierz dostawcę lub grupę dostawców, do których mają zastosowanie warunki zatrzymania płatności. W przypadku wybrania opcji **Wszystkie** w poprzednim kroku, to pole będzie niedostępne.
5. W polu **Warunki retencji dostawcy** wybierz warunek zatrzymania utworzony w poprzedniej procedurze.
6. Jeśli w projekcie skonfigurowano również warunki płatności po zapłacie (PWP) dla dostawcy, wprowadź procent progowy dla projektu w polu **Wartość procentową progu PWP**.

Warunki zatrzymania płatności dla dostawcy widnieją również na zamówieniach zakupu utworzonych dla danego dostawcy.
