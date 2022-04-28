---
title: Tworzenie funkcji globalizacji
description: W tym temacie wyjaśniono, jak utworzyć funkcję globalizacji.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 94038b0eb412632c348081bbf467f44310d9e955
ms.sourcegitcommit: 6109fc2fe5f407363bb6f240d64b7214657f5914
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/15/2022
ms.locfileid: "8603033"
---
# <a name="create-a-globalization-feature"></a>Tworzenie funkcji globalizacji

[!include [banner](../includes/banner.md)]

Możesz utworzyć funkcję fakturowania elektronicznego od podstaw lub możesz oprzeć ją na istniejącej funkcji. Podczas tworzenia funkcji od podstaw należy ręcznie dodać konfiguracje raportowania elektronicznego (ER) i inne składniki, takie jak konfiguracja funkcji i szczegóły konfiguracji aplikacji. Podczas tworzenia funkcji opartej na istniejącej funkcji nowa funkcja dziedziczy wszystkie konfiguracje i parametry funkcji podstawowej. Możesz przejrzeć zawartość skopiowaną z funkcji podstawowej do nowej funkcji.

## <a name="create-a-feature-from-scratch"></a>Utwórz funkcję od podstaw

W tej sekcji wyjaśniono, jak utworzyć funkcję fakturowania elektronicznego, gdy żadna funkcja globalizacji nie jest dostępna w globalnym repozytorium dla scenariuszy biznesowych po wyjęciu z pudełka.

Aby utworzyć funkcję fakturowania elektronicznego, wykonaj następujące kroki.

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. Wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Nowa funkcja**.
4. Wprowadź nazwę i opis dla funkcji Elektroniczne fakturowanie.
5. Wybierz opcję **Utwórz funkcję**. Pierwsza wersja nowej funkcji jest wyświetlana po prawej stronie strony i ma stan **Wersja robocza**.

    Następnie należy dodać konfiguracje ER i konfiguracje funkcji. Przed dodaniu nowych lub istniejących konfiguracji formatów ER należy upewnić się, że istnieją w lokalnym repozytorium RCS.

6. Wybierz opracowywaną funkcję fakturowania elektronicznego.
7. Na karcie **Konfiguracje** wybierz pozycję **Dodaj**.
8. W siatce **Konfiguracje** odszukaj i wybierz konfiguracje formatów wymagane do przetwarzania potoku (na przykład do generowania plików faktur elektronicznych lub odpowiedzi na przetwarzanie odpowiedzi z zewnętrznych usług sieci web).
9. Kliknij przycisk **OK**. Teraz możesz używać konfiguracji w akcjach potoku przetwarzania. Aby uzyskać więcej informacji na temat szablonów, zobacz [Praca z konfiguracjami](e-invoicing-work-configurations.md).
10. Aby dodać konfigurację funkcji fakturowania elektronicznego, utwórz ją na karcie **Ustawienia** na **stronie Nowa funkcja**. Aby uzyskać więcej informacji, zobacz [Pracuj z ustawieniami funkcji](e-invoicing-feature-setup.md).
11. Zakończ konfigurację i wdróż funkcję fakturowania elektronicznego w środowisku usług. Aby uzyskać więcej informacji, zobacz [Zakończenie, publikacja i wdrożenie funkcji globalizacji](e-invoicing-complete-publish-deploy-globalization-feature.md).

### <a name="create-file-format-configurations-that-are-derived-from-the-existing-invoice-model"></a>Tworzenie konfiguracji formatu plików, które są wyprowadzane z istniejącego modelu faktury

Tę sekcję można pominąć, jeśli nie trzeba tworzyć konfiguracji ER, ale można użyć ich ponownie jako podstawy.

Ta procedura pokazuje, jak utworzyć konfiguracje formatu plików, które są wymagane dla nowej funkcji fakturowania elektronicznego, którą chcesz utworzyć. Utwórz konfigurację formatu pliku faktury elektronicznej i wszelkie inne konfiguracje formatu pliku wymagane przez nową funkcję fakturowania elektronicznego.

1. Zaloguj się do swojego konta RCS.
2. W obszarze roboczym **raportowanie elektroniczne** wybierz kafelek **konfiguracje raportowania**.
3. Wybierz **model faktury** lub, w przypadku scenariuszy brazylijskich, wybierz **model obrachunkowy**.
4. Wybierz **Utwórz konfigurację**, a następnie w rozwijanym oknie dialogowym wybierz opcję **Format na podstawie faktury modelu danych**.
5. Wprowadź nazwę i opis dla konfiguracji formatu.
6. W polu **Typ formatu** wybierz typ rozszerzenia pliku.
7. W polu **Definicja modelu danych** wybierz strukturę główną, do których ma być mapowany format. Na przykład **InvoiceCustomer** jest używana w formatach faktur dla odbiorcy.
8. Wybierz **Utwórz konfigurację**.
9. Wybierz nową konfigurację formatu.
10. Wybierz opcję **Projektant i użyj narzędzia Projektant formatu**, aby skonfigurować układ pliku tak, aby był zgodny ze specyfikacjami formatu pliku.
11. Zamknij stronę.
12. W obszarze **wersje** na skróconej karcie wybierz opcję **Zmień stan** \> **Zakończ**.
13. Wybierz pozycję **Zmień stan** \> **Udostępnij**, aby opublikować konfigurację formatu w repozytorium globalnym.

Nowe konfiguracje formatu plików muszą być udostępnione w domenie Microsoft, zanim będą mogły zostać wykorzystane przez usługę fakturowania elektronicznego.

1. Wybierz konfigurację formatu, nad którą pracujesz. Stan konfiguracji musi być **udostępniony**.
2. Na karcie **Wersje** wybierz pozycję **Zaawansowane udostępnianie** \> **Globalne repozytorium**.
3. Na karcie **Udostępnione** wybierz pozycję **Organizacje**.
4. W polu **Parametry** wprowadź **microsoft.com**, aby udostępnić konfigurację formatu domenie firmy Microsoft.
5. Kliknij przycisk **OK**.

## <a name="create-a-feature-that-is-based-on-an-existing-feature"></a>Tworzenie funkcji opartej na istniejącej funkcji

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.
3. W polu **Dostawca konfiguracji** upewnij się, że jest wybrany aktywny dostawca konfiguracji. W ten sposób nowa funkcja fakturowania elektronicznego pojawi się na liście po jej utworzeniu. Jeśli aktywny dostawca konfiguracji nie jest wybrany, nowa funkcja zostanie odfiltrowana z listy.
4. Wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Na podstawie istniejącej wersji**.
5. Wprowadź nazwę i opis funkcji.
6. W polu **Funkcja podstawowa** wybierz podstawową wersję tej funkcji.
7. Wybierz opcję **Utwórz funkcję**. Funkcja jest tworzona i ma stan **Wersja robocza**.
8. Przejrzyj składniki funkcji, aby określić, czy aktualizacje są wymagane:

    - Przejrzyj konfiguracje, na wypadek potrzeby dostosowania formatów ER i ich powiązania ich z mapowaniami formatu dla wersji funkcji.
    - Przejrzyj ustawienia, jeśli chcesz dostosować kartę **Akcje**, kartę **Reguły stosowania** lub **Zmienne** dla wersji funkcji.

9. Zakończ konfigurację i wdróż funkcję fakturowania elektronicznego w środowisku usług. Aby uzyskać więcej informacji, zobacz [Zakończenie, publikacja i wdrożenie funkcji globalizacji](e-invoicing-complete-publish-deploy-globalization-feature.md).
