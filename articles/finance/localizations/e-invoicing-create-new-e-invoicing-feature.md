---
title: Tworzenie nowej funkcji fakturowania elektronicznego
description: Ten temat wyjaśnia, jak utworzyć nową funkcję fakturowania elektronicznego, gdy nie jest dostępna żadna konfigurowalna funkcja dla danego kraju lub regionu.
author: gionoder
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ffef49c78fd0564db7a2329580ad33a9ccc633c8ac74557e625d1cfb29931576
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744942"
---
# <a name="create-a-new-electronic-invoicing-feature"></a>Tworzenie nowej funkcji fakturowania elektronicznego

[!include [banner](../includes/banner.md)]

Ten temat wyjaśnia, jak utworzyć nową funkcję fakturowania elektronicznego, gdy nie jest dostępna żadna konfigurowalna funkcja dla danego kraju lub regionu.

Aby utworzyć nową funkcję fakturowania elektronicznego, wykonaj poniższe zadania:

1. Utwórz nową konfigurację formatu pliku, używając dostarczonej konfiguracji modelu faktury i korzystając z istniejącego mapowania faktury dla funkcji, którą chcesz utworzyć.
2. Dodaj konfiguracje formatu pliku do konfiguracji funkcji Fakturowanie elektroniczne.
3. Utwórz konfigurację funkcji fakturowania elektronicznego.
4. Ukończ nową funkcję Elektroniczne fakturowanie i opublikuj ją w globalnym repozytorium dla swojej organizacji.
5. Wdrożenie nowej funkcji fakturowania elektronicznego do środowiska usługowego.

## <a name="create-new-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Tworzenie nowych konfiguracji formatu plików, które są wyprowadzane z istniejącego modelu faktury

W tej procedurze utworzysz konfiguracje formatu plików, które są wymagane dla nowej funkcji fakturowania elektronicznego, którą chcesz utworzyć. Można utworzyć konfigurację formatu pliku faktury elektronicznej oraz wszelkie inne konfiguracje formatu pliku, których może wymagać nowa funkcja fakturowania elektronicznego.

Przed rozpoczęciem tej procedury zaloguj się do konta Regulatory Configuration Service (RCS).

1. W Microsoft Dynamics 365 Finance, w obszarze roboczym **Raportowanie elektroniczne** na kafelku dostawcy konfiguracji Litware, Inc. wybierz opcję **Repozytoria**, a następnie **Microsoft** jako dostawcę konfiguracji.
2. Wybierz opcję **Globalne**, wybierz pozycję **Otwórz**, a następnie w lewym okienku wybierz **konfigurację modelu faktury**.

    > [!IMPORTANT]
    > Dla Brazylii wybierz konfigurację modelu **dokumentów fiskalnych**.

3. Na karcie **Konfiguracje** wybierz pozycję **Import**.
4. Zamknij stronę.
5. Zamknij stronę.
6. Wybierz kafelek **Konfiguracje raportowania**, a następnie wybierz zaimportowany model faktury.
7. Wybierz pozycję **Utwórz konfigurację**, a następnie wybierz pozycję **Format na podstawie modelu kontekstu faktury**.
8. Wprowadź nazwę i opis dla konfiguracji formatu.
9. W polu **Typ formatu** wybierz typ rozszerzenia pliku.
10. Wybierz **Utwórz konfigurację**, a następnie wybierz utworzoną konfigurację formatu.
11. Wybierz opcję **Projektant i użyj narzędzia Projektant formatu**, aby skonfigurować układ pliku tak, aby był zgodny ze specyfikacjami formatu pliku.
12. Zamknij stronę.
13. W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan** \> **Zakończ**.
14. Wybierz pozycję **Zmień stan** \> **Udostępnij**, aby opublikować konfigurację formatu w repozytorium globalnym.

Nowa konfiguracja formatu pliku musi być współużytkowana z domeną firmy Microsoft, zanim konfiguracja będzie mogła być wykorzystana przez usługę fakturowania elektronicznego.

1. Wybierz konfigurację formatu, nad którą pracujesz. Stan konfiguracji musi być **udostępniony**.
2. Na karcie **Wersje** wybierz pozycję **Zaawansowane udostępnianie** \> **Globalne repozytorium**.
3. Na karcie **Udostępnione** wybierz pozycję **Organizacje**.
4. W polu **Parametry** wprowadź **Microsoft.com**, aby udostępnić konfigurację formatu domenie firmy Microsoft.
5. Kliknij przycisk **OK**.

## <a name="create-the-new-electronic-invoicing-feature"></a>Tworzenie nowej funkcji fakturowania elektronicznego

1. W RCS otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
2. Wybierz opcję **Dodaj odbiorcę**, a następnie wybierz **Nowa funkcja**.
3. Wprowadź nazwę i opis dla funkcji Elektroniczne fakturowanie.
4. Wybierz opcję **Utwórz funkcję**.

## <a name="add-electronic-invoicing-feature-configurations"></a>Dodawanie konfiguracji funkcji Faktur elektronicznych

1. Wybierz opracowywaną funkcję fakturowania elektronicznego.
2. Na karcie **Konfiguracje** wybierz pozycję **Dodaj**.
3. W siatce **Konfiguracje** przejrzyj i wybierz konfiguracje formatu pliku, które są wymagane przez funkcję fakturowania elektronicznego do wygenerowania pliku faktury elektronicznej.
4. Kliknij przycisk **OK**.

## <a name="add-electronic-invoicing-feature-setups"></a>Dodawanie ustawień funkcji Faktur elektronicznych

1. Na karcie **Ustawienia** wybierz pozycję **Dodaj**, a następnie wybierz pozycję **Ustawienia niestandardowe**.
2. Wprowadź nazwę i opis funkcji konfiguracji.
3. W polu **Typ instalacji** wybierz opcję **Potok przetwarzania**.
4. Wybierz opcję **Utwórz**.
5. Wybierz konfigurację, nad którą pracujesz, a następnie wybierz opcję **Edytuj**.
6. Na karcie **Potok przetwarzania** wybierz pozycję **Nowy**, aby dodać akcję potoku. Aby uzyskać więcej informacji o potokach, zobacz temat [Akcje](e-invoicing-configuration-rcs.md#actions).
7. Wybierz kartę **Reguły stosowania** i wybierz **Nowa**, aby wyświetlić i zachować reguły klasy. Aby uzyskać więcej informacji na temat reguł stosowania, zobacz [Reguły stosowania](e-invoicing-configuration-rcs.md#applicability-rules).
8. Na karcie **Zmienne** wybierz pozycję **Nowa**, aby dodać zmienne zgodnie z wymaganiami.
9. Wybierz pozycję **Zapisz**, a następnie wybierz pozycję **Sprawdź poprawność**, aby sprawdzić spójność konfiguracji.
10. Zamknij stronę.

## <a name="deploy-the-electronic-invoicing-feature-to-the-service-environment"></a>Wdrożenie nowej funkcji fakturowania elektronicznego do środowiska usługowego

Aby uzyskać informacje dotyczące sposobu wykonywania tego zadania, zobacz [Wdrażanie funkcji fakturowania elektronicznego w środowisku usługi](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="deploy-the-electronic-invoicing-feature-to-a-connected-application"></a>Wdrażanie funkcji fakturowania elektronicznego w połączonej aplikacji

Aby uzyskać informacje dotyczące sposobu wykonywania tego zadania, zobacz [Konfigurowanie konfiguracji aplikacji](e-invoicing-get-started.md#configure-the-application-setup) i [Wdrażanie funkcji fakturowania elektronicznego w połączonej aplikacji](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application).
