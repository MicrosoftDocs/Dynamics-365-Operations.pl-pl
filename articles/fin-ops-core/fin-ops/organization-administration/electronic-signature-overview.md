---
title: Omówienie podpisów elektronicznych
description: Ten artykuł zawiera omówienie podpisów elektronicznych, a także opis sposobu ich używania.
author: maertenm
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df7f842477ddfb88662f37ae311215f08c6b0173
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693191"
---
# <a name="electronic-signatures-overview"></a>Omówienie podpisów elektronicznych

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie podpisów elektronicznych, a także opis sposobu ich używania.

## <a name="what-is-an-electronic-signature"></a>Co to jest podpis elektroniczny?

Podpis elektroniczny potwierdza tożsamość osoby, która ma rozpocząć lub zatwierdzić jakiś proces obliczeniowy. W przypadku niektórych branż podpis elektroniczny jest tak samo prawnie wiążący jak podpis odręczny.

Podpisy elektroniczne są wymagane przepisami w przypadku kilku branż regulowanych, takich jak przemysł farmaceutyczny, spożywczy oraz lotniczy i obronny. Wymagają ich również przepisy 21 CFR część 11 wydane przez amerykańską Agencję ds. Żywności i Leków (FDA).

> [!NOTE]
> Sam podpis elektroniczny nie jest tym samym, co podpis cyfrowy. Podpis elektroniczny jest po prostu substytutem podpisu odręcznego, podczas gdy podpis cyfrowy stanowi dodatkowy środek zabezpieczeń. Podpis cyfrowy pomaga w ustaleniu, czy inny użytkownik lub proces nie naruszył danych. Podpis cyfrowy może być również weryfikowany i ta weryfikacja nie może zostać zakwestionowana przez właściciela certyfikatu użytego do podpisania danych. Jak opisano poniżej, podpisy elektroniczne mają wbudowaną funkcjonalność podpisu cyfrowego.

## <a name="electronic-signatures"></a>Podpisy elektroniczne

Można używać podpisów elektronicznych w przypadku procesów biznesowych o podstawowym znaczeniu. Niektóre procesy mają wbudowane możliwości podpisu elektronicznego. Można również tworzyć niestandardowe wymagania dotyczące podpisu cyfrowego dla dowolnej tabeli lub pola bazy danych.

Podpisy elektroniczne mają wbudowaną funkcjonalność podpisu cyfrowego. Każdy użytkownik, który podpisuje dokumenty, musi uzyskać prawidłowy certyfikat kryptograficzny. Podczas podpisywania dokumentu sprawdzana jest poprawność klucza prywatnego skojarzonego z tym certyfikatem. Informacje dotyczące podpisów elektronicznych są rejestrowane w dzienniku inspekcji. Aby skonfigurować podpisy elektroniczne, zobacz [Konfigurowanie podpisów elektronicznych](tasks/set-up-electronic-signatures.md).

## <a name="users-who-require-access-to-electronic-signatures"></a>Użytkownicy, którzy potrzebują dostępu do podpisów elektronicznych

Trzy rodzaje użytkowników zwykle wymagają dostępu zabezpieczeń do podpisów elektronicznych: administratorzy podpisów elektronicznych, osoby podpisujące i audytorzy podpisów elektronicznych.

### <a name="electronic-signature-administrator"></a>Administrator podpisów elektronicznych

Administrator podpisów elektronicznych konfiguruje wymagania dotyczące podpisów, parametry ogólne i osoby zatwierdzające, a ponadto otrzymuje alerty w przypadku, gdy nie można sprawdzić poprawności podpisu. Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Menedżer ds. informatyki** ma uprawnienie do zarządzania podpisami elektronicznymi.

### <a name="signer"></a>Osoba podpisująca

Osoba podpisująca składa podpisy elektroniczne w przypadku dokumentów i procesów wymagających podpisów. Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Użytkownik systemu**, ma uprawnienie do korzystania z elektronicznych podpisów dokumentów.

> [!NOTE]
> Osoba podpisująca może wymagać dodatkowych uprawnień, aby uzyskać dostęp do danych związanych z podpisywanym dokumentem lub procesem. Użytkownik, który wprowadza zmiany w danych i musi je następnie podpisać, musi mieć uprawnienie do modyfikacji danych. Użytkownik, który ma podpisywać zmiany w imieniu innego użytkownika, może nie wymagać dostępu do danych. Przykładem tego rodzaju użytkownika jest inspektor, który podpisuje zmiany pracownika.

### <a name="electronic-signature-auditor"></a>Audytorów podpisów elektronicznych

Audytor podpisów elektronicznych przegląda dziennik bazy danych oraz dziennik przeglądu podpisów, który jest dostępny z dziennika bazy danych. Domyślnie każdy użytkownik, który należy do roli zabezpieczeń **Menedżer ds. informatyki** ma uprawnienie do inspekcji podpisów elektronicznych.

Jeśli używasz innych ról niż **Menedżer ds. informatyki**, upewnij się, że przypisano roli następujące uprawnienia:

- Przeglądanie błędów podpisu elektronicznego
- Przeglądanie dziennika bazy danych

## <a name="signing-documents-electronically"></a>Elektroniczne podpisywanie dokumentów

### <a name="get-a-certificate"></a>Uzyskiwanie certyfikatu

Aby móc elektronicznie podpisywać dokumenty, musisz zażądać certyfikatu.

> [!NOTE]
> Funkcje Microsoft SQL Server są używane do tworzenia certyfikatów i włączania funkcjonalności podpisu cyfrowego. Nie jest wymagana żadna dodatkowa infrastruktura certyfikatów czy kluczy publicznych (PKI).

Gdy zażądasz certyfikatu, są dla Ciebie tworzone klucze publiczny i prywatny. Klucz prywatny jest zaszyfrowany przy użyciu hasła znanego tylko Tobie. Gdy podpisujesz dokument elektronicznie, Twoja tożsamość jest weryfikowana podczas wprowadzenia hasła.

Aby zażądać certyfikatu, na stronie **Opcje** na karcie **Konta** kliknij przycisk **Pobierz certyfikat**.

Musisz wprowadzić i potwierdzić hasło, którego będziesz używać do składania podpisu. To hasło służy do ochrony klucza prywatnego i upoważnia do użycia certyfikatu. Nie jest ono przechowywane w bazie danych i nie jest dostępne nikomu innemu, w tym również administratorowi.

W razie zapomnienia hasła połączonego z certyfikatem należy zresetować certyfikat. Zresetowanie certyfikatu nie wpływa na dokumenty podpisane przy użyciu poprzedniego certyfikatu. Aby zresetować certyfikat, na stronie **Opcje** kliknij przycisk **Resetuj certyfikat**.

### <a name="sign-a-document-electronically"></a>Elektroniczne podpisywanie dokumentu

W przypadku dokonania zmiany wymagającej podpisu elektronicznego wyświetlana jest strona **Podpisz dokument**.

1. Na stronie **Podpisz dokument** kliknij kartę **Dokument**, aby przejrzeć zmiany dokonane w dokumencie.
2. Na karcie **Podpis** wybierz kod przyczyny.
3. Wprowadź komentarz, jeśli jest wymagany.
4. Jeśli Twój identyfikator użytkownika nie jest wyświetlany w polu **Osoba podpisująca**, wybierz go z listy.
5. Wprowadź swoją lokalizację, jeśli ta informacja jest wymagana.
6. Kliknij przycisk **OK**

### <a name="sign-for-another-users-changes"></a>Podpisywanie zmian dokonanych przez innego użytkownika

Czasami możesz chcieć podpisać zmiany dokonane przez innego użytkownika. Na przykład przełożony może mieć obowiązek podpisywania zmian wprowadzonych przez pracownika na liście składowej (BOM). Niniejszej procedury należy użyć, aby wyznaczyć użytkownika na osobę podpisującą dla innego użytkownika.

> [!NOTE]
> Jeśli użytkownik podpisuje zmianę dokonaną przez innego użytkownika, podpis musi zostać złożony na stacji roboczej użytkownika, który dokonał zmiany. Użytkownik ten będzie miał możliwości zapisania zmiany dopiero po złożeniu podpisu.

Aby wyznaczyć osoby zatwierdzające, wykonaj następujące kroki:

1. Na stronie **Opcje** na karcie **Konta** kliknij opcję **Wyznacz osobę zatwierdzającą**.
2. W polu **Identyfikator użytkownika osoby zatwierdzającej** wybierz identyfikator użytkownika, który ma podpisywać zmiany dokonane przez innego użytkownika.
3. W polu **Identyfikator użytkownika osoby potrzebującej podpisu** wybierz identyfikator użytkownika, którego zmiany mają być podpisywane.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]