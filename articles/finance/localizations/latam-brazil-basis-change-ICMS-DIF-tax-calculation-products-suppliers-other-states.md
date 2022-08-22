---
title: Zmiana podstawy w obliczeniach podatku ICMS-DIF dla produktów od dostawców z innych stanów
description: W tym artykule opisano konfigurację obliczania typu podatku ICMS-DIF w przypadku, gdy dokument fiskalny jest odbierany w brazylijskim stanie Rio Grande do Sul (RS) lub São Paulo (SP).
author: Kai-Cloud
ms.date: 06/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-1-17
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 1bd9982a3804778a27203b4311682ee8bc3c4841
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218659"
---
# <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-from-suppliers-in-other-states"></a>Zmiana podstawy (podwójna podstawa) w obliczeniach podatku ICMS-DIF dla produktów od dostawców z innych państw

W tym artykule opisano konfigurację obliczania typu podatku **ICMS-DIF** w przypadku, gdy dokument fiskalny jest odbierany w brazylijskim stanie Rio Grande do Sul (RS) lub São Paulo (SP).

Zgodnie z definicją w ustawie państwowej zebranemu przez system Imposto sobre Tychulação de Mercadorias e Serviços (ICMS) należy użyć następującej reguły:

*ICMS do zbierania* = ([(*Kwota operacji* – *ICMS ze źródła*) ÷ (1 – *ICMS % wewnętrzny*)] × *ICMS % wewnętrznych*) – kwota *ICMS ze źródła*

## <a name="example"></a>Przykład

Firma brazylijskia ze stanem RS otrzymuje dokument fiskalny na zakup od dostawcy ze stanem SP. Firma musi zbierać procentową różnicę między ICMS między województwem RS (18 procent) a województwem SP (12 procent). Podstawa musi być jednak obliczona zgodnie z poprzednią regułą.

- **Kwota operacji:** 1 000,00 realiów brazylijskich (R$ 1 000,00)
- **Stan międzystanowy ICMS:** 120,00 USD
- **Procent ICMS w stanie RS:** 18 procent
- **ICMS do odbioru w województwie:** (\[(1000 – 120) ÷ (1 – 0,18)\] × 0,18 ) – 120 = R$ 73,17 

## <a name="resolution"></a>Rozwiązanie

Aby obliczyć kwotę różnicy ICMS (ICMS-DIF) zgodnie z regułami stanu RS, należy skonfigurować kody podatków oraz grupę podatków w następujący sposób:

1. Umożliwia utworzenie kodu podatku służącego do otrzymywania 12-procentowego podatku ICMS (dla drugiego województwa). Ten kod służy do rejestrowania kwoty podatku dochodowego od dostawcy.
2. Utwórz kod podatku, aby zbierać ICMS-DIF. Ten kod podatku powinien mieć kwotę procentową w wysokości 18 procent (dla własnego województwa), aby zdefiniować różnicę między 18 a 12 procentami. Ustaw typ podatku **ICMS-DIF**. Ten kod podatku musi być zdefiniowany w następujący sposób w parametrach obliczania:

    - W polu **Pochodzenie** wybierz pozycję **Procent od kwoty brutto**.
    - W polu **Podstawa marginesu** wybierz kwotę **netto na wiersz**.
    - Kod opodatkowania należy zdefiniować tak, aby jego wartość podatkowa wynosi **3**. W ten sposób transakcja korekty zostanie utworzona automatycznie po włączeniu **modułu Księgi podatkowe**.
    - W konfiguracji grupy podatków wybierz opcję **Użyj podatku** dla kodu podatku **ICMS-DIF**.

### <a name="use-the-delta-tax-rate-in-the-configuration-of-dual-base-icms-dif-sales-tax-codes"></a>Użyj stawki podatku delta w konfiguracji dwubazowych kodów podatku od sprzedaży ICMS-DIF

Gdy używane są uprzednio opisane ustawienia, **kod podatku ICMS-DIF** będzie obliczany w dwóch regułach podstawowych. Jednak nominalna stawka podatku wynosi 18 procent, co różni się od stawki 6 procent w prostej regułach podstawowych. Ta różnica powoduje niespójność w dokumentach fiskalnych i raportach podatkowych. Od wersji Microsoft Dynamics 365 Finance 10.0.29 można włączyć **(Brazylia) Skonfiguruj stawkę podatku delta w kodzie podatku ICMS-DIF dla przypadku podwójnej podstawy** w **Zarządzanie funkcjami**, aby usunąć niezgodność.

- Oprócz wykonania kroków opisanych w poprzedniej sekcji wybierz kod podatku **ICMS 12** w polu **Podatek od sprzedaży**.
- Ustaw stawkę podatku dla kodu podatku **ICMS-DIF** na 18 procent. W **polu Procent/Kwota** zostanie pokazanie stawki podatku nominalnego jako 6 procent.

> [!NOTE]
> Kody **podatków ICMS-DIF** i **ICMS 12** muszą być przypisane w tej samej grupie podatków.

## <a name="basis-change-dual-base-in-icms-dif-tax-calculations-for-products-to-non-taxpayer-consumers-difal-in-other-states"></a>Zmiana podstawy (podwójna podstawa) w obliczeniach podatku ICMS-DIF dla produktów dla konsumentów niebędących podatnikami (DIFAL) w innych stanach

Włącz funkcję **(Brazylia) Obliczanie podwójnej wartości bazowej dla ICMS-DIFAL w transakcjach sprzedaży** w **Zarządzaniu funkcjami** w celu obsługi zmiany bazy ICMS-DIF w transakcjach z klientami niebędącymi podatnikami z innego stanu. Przykładowy kod podatku ICMS-DIF zaczyna obowiązywać w transakcjach zamówień sprzedaży i fakturach wolnych.

Włącz funkcję **(Brazylia) Obliczanie podwójnej wartości bazowej dla ICMS-DIUJE dla spraw IPI** w **Zarządzanie funkcjami** w celu obsługi scenariuszy, w których handel z konsumentami niebędącymi podatnikami z innego stanu jest również odpowiedzialny za Imposto sobre Produtos Industrializados (IPI). Kwota podatku o kodzie podatku IPI zostanie rozpoznana i zastosowana w podstawie podatku ICMS-DIFAL.

- W nagłówku zamówienia sprzedaży lub faktury niezależnej, na **Informacje podatkowe** skróconej karty, opcja **Użytkownik końcowy** musi być ustawiona na **Tak**.
- W nagłówku zamówienia zakupu lub faktury od dostawcy na **Informacje podatkowe** skróconej karty, opcja **Użytkowanie i konsumpcja** musi być ustawiona na **Tak**.
