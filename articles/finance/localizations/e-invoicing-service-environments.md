---
title: Środowiska usługi
description: Ten temat zawiera informacje o środowiskach usług dla fakturowania elektronicznego i wyjaśnia, jak je skonfigurować.
author: dkalyuzh
ms.date: 02/28/2022
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
ms.openlocfilehash: a8a135098f71e1413cd20ff8ad4003f090ae3407
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371795"
---
# <a name="service-environments"></a>Środowiska usługi

[!include [banner](../includes/banner.md)]

Środowiska usługowe to partycje logiczne, które są tworzone w celu obsługi funkcji globalizacji i odpowiednich dokumentów przetwarzanych w usłudze fakturowania elektronicznego. Sekrety bezpieczeństwa i certyfikaty cyfrowe oraz uprawnienia dostępu (zarządzanie) muszą być skonfigurowane na poziomie środowiska usługi.

Możesz utworzyć tyle środowisk usług, ile potrzebujesz. Wszystkie tworzone przez Ciebie środowiska usług są od siebie niezależne. Zalecane jest utworzenie co najmniej dwóch środowisk serwisowych:

- Jedno ze środowisk głównych na potrzeby developmentu i sprawdzania poprawności. To środowisko jest zazwyczaj środowiskiem testowania akceptacji użytkownika (UAT).
- Jedno środowisko do celów produkcyjnych. To środowisko jest zazwyczaj środowiskiem produkcyjnym.

Ten typ partycjonowania pomaga zapewnić, że procesy fakturowania elektronicznego zostały zweryfikowane i dostosowane w piaskownicy przed ich rozpoczęciem w produkcji.

Środowiska usług muszą być tworzone i utrzymywane w usłudze Regulatory Configuration Service (RCS). Następnie, gdy będą gotowe, muszą zostać opublikowane w usłudze Fakturowania Elektronicznego. Proces publikowania wysyła parametry środowiska usługi z wystąpienia usługi RCS do usługi fakturowania elektronicznego.

Jeśli nie ukończysz procesu publikowania po utworzeniu nowego środowiska usługi lub dostosowaniu istniejącego środowiska usługi (na przykład przez dodanie lub usunięcie użytkowników lub kluczy tajnych Microsoft Azure Key Vault), zmiany nie będą obowiązywać. Tylko środowiska opublikowane są dostępne przez Dynamics 365 Finance lub Dynamics 365 Supply Chain Management.

## <a name="service-environment-statuses"></a>Stany środowiska usługi

Środowiskami usług można zarządzać za pomocą stanu. Stan środowiska można wyświetlić na **stronie Środowiska usługi**. Dostępne są następujące stany:

- **Nie opublikowano** — środowisko zostało utworzone, ale nie zostało jeszcze opublikowane.
- **Opublikowano** — środowisko zostało opublikowane w dodatku Fakturowanie elektroniczne.
- **Zmienione** — Atrybuty opublikowanego środowiska zostały zmienione, ale zmiany nie zostały jeszcze opublikowane.

## <a name="users"></a>Użytkownicy

Każde środowisko usług musi zawierać listę użytkowników, którzy mogą łączyć się z fakturowaniem elektronicznym z poziomu finansów lub Supply Chain Management.

## <a name="applications"></a>Aplikacje

W niektórych scenariuszach aplikacje inne niż finanse lub Supply Chain Management mogą wymagać połączenia z usługą fakturowania elektronicznego w celu przesyłania dokumentów elektronicznych do dalszego przetwarzania lub pobierania informacji, takich jak stan przesyłania dokumentu. W tych scenariuszach aplikacja powinna być zdefiniowana na liście aplikacji. W ten sposób będzie miał dostęp do usługi fakturowania elektronicznego. Aplikacja musi być również zarejestrowana jako aplikacja w Azure Active Directory (Azure AD), a do jej identyfikacji musi być używany identyfikator obiektu. 

Ponieważ firma Microsoft wymaga wysokiego poziomu kontroli zabezpieczeń nad aplikacjami, które mogą łączyć się z usługą fakturowania elektronicznego, należy skontaktować się z firmą Microsoft pod adresem <DGXRegulatoryservicesengineering@service.microsoft.com> i podać następujące szczegóły dotyczące aplikacji:

- Identyfikator dzierżawcy usługi Azure AD
- Identyfikator środowiska usługi Microsoft Dynamics Lifecycle Services (LCS)
- Identyfikator aplikacji (identyfikator klienta)
- Identyfikator obiektu
- Uzasadnienie i opis aplikacji wysokiego poziomu

Firma Microsoft oceni żądanie i zarejestruje aplikację w rejestrze zabezpieczeń, aby zagwarantować, że będzie ona działać z fakturowaniem elektronicznym.

## <a name="number-sequences"></a>Sekwencje numerów

Jeśli scenariusze wymagają sekwencji numerów (na przykład w nazwach plików), można używać sekwencji numerów zdefiniowanych dla określonego środowiska, ale których można używać we wszystkich funkcjach globalizacji lub dla określonej funkcji globalizacji. Po określonej sekwencji numerów można jej używać w zmiennych i procesach przetwarzania. Aby śledzić ich użycie, na **stronie Sekwencje numerów** poszukaj wartości **Bieżące** dla parametru **W użyciu**.

### <a name="working-with-number-sequences"></a>Praca z sekwencjami numerów
Na stronie **Sekwencje numerów**: 

- Wybierz pozycję **Nowy**, aby utworzyć sekwencje numerów. Następnie wprowadź nazwę i opis. 
- Wybierz **polecenie Usuń**, aby usunąć sekwencję numerów, jeśli nie jest już używana.
- Nie musisz wybierać opcji **Publikuj** w okienku akcji, aby opublikować zmiany w sekwencji numerów. Aktualizacja odbywa się automatycznie.

## <a name="create-a-key-vault-reference"></a>Utwórz odwołanie do usługi Key Vault

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Faktury elektroniczne**.
3. Na stronie **Ustawienie środowiska** w okienku akcji wybierz pozycję **Środowiska usługi**.
4. Na stronie **Środowiska usługi**, w okienku akcji wybierz Środowisko usługi **Parametry Key Vault**.
5. Na stronie **Parametry usługi Key Vault**, a następnie wybierz opcję **Nowy**, aby utworzyć klucz tajny Key Vault.
6. W polu **Nazwa** wprowadź nazwę wpisu tajnego magazynu kluczy referencji.
7. W polu **Opis wprowadź** opis.
8. W polu **Key Vault URI** wklej identyfikator URI Key Vault z magazynu kluczy (`https://<your key vault>.vault.azure.net/`). Aby uzyskać więcej informacji, przejrzyj temat [Utwórz magazyn kluczy platformy Azure w portalu Azure](e-invoicing-create-azure-key-vault-azure-portal.md).
9. Wybierz opcję **Zapisz**.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>Utwórz tajny token konta magazynu

1. Wybierz **Parametry wpisu tajnego**, wybierz odwołanie Key Vault utworzone w poprzedniej procedurze i w sekcji **Certyfikaty** wybierz opcję **Dodaj**.
2. W polu **Nazwa** wprowadź ten nazwę klucza tajnyego konta magazynu. Ta nazwa powinna być taka sama jak nazwa klucza tajnego klucza, który zawiera token sygnatury dostępu współdzielonego (SAS). Aby uzyskać więcej informacji, przejrzyj temat [Utwórz konto magazynu platformy Azure w portalu Azure](e-invoicing-create-azure-storage-account-azure-portal.md). 
3. W polu **Opis wprowadź** opis.
4. W polu **Typ** wybierz **Wpis tajny**.
5. Wybierz opcję **Zapisz**.
    
## <a name="create-a-service-environment"></a>Tworzenie środowiska usługi

1. Na stronie **Środowiska usługowe** w okienku akcji wybierz pozycję **Nowe**, by stworzyć środowisko usługi.
2. W polu **Nazwa** wprowadź nazwę środowiska e-fakturowania.
3. W polu **Opis wprowadź** opis.
4. W polu **Tajny klucz tokenu sygnatury dostępu Współdzielonego magazynu** wybierz nazwę klucza tajnego konta magazynu, który musi być używany do uwierzytelniania dostępu do konta magazynu.
5. W sekcji **Użytkownicy** wybierz opcję **Dodaj**, aby dodać użytkownika, który może przesyłać faktury elektroniczne za pośrednictwem środowiska, a także połączyć się z kontem magazynu.
6. W polu **Identyfikator użytkownika** wprowadź alias użytkownika. 
7. W polu **Adres e-mail** wprowadź adres e-mail dla użytkownika.
8. Wybierz opcję **Zapisz**.
9. W okienku akcji wybierz opcję **Publikuj**, aby opublikować środowisko na serwerze dodatku Faktury elektroniczne. Sprawdź, czy wartość pola **Stan** jest zmieniana na **Opublikowana**.
