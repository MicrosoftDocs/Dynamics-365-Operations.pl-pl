---
title: Konfigurowanie i obsługa współpracy z dostawcami
description: W tym temacie opisano sposób konfigurowania zasad współpracy z dostawcą w Dynamics 365 Supply Chain Management. Wyjaśniono również, jak konfigurować nowych użytkowników współpracujących z dostawcami i zarządzać rolami zabezpieczeń dla tych użytkowników.
author: Henrikan
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b635255fffa6fd3c6612cd248dc692df204aa76d
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652068"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Konfigurowanie i obsługa współpracy z dostawcami

[!include [banner](../includes/banner.md)]

Interfejs współpracy z dostawcami udostępnia użytkownikom zewnętrznym ograniczony zestaw informacji o zamówieniach zakupu, fakturach i zapasach konsygnacyjnych. Z tego interfejsu sprzedawca może również odpowiadać na zapytania ofertowe (RFQ) oraz przeglądać i edytować podstawowe informacje o firmie.

W tym temacie opisano sposób konfigurowania zasad współpracy z dostawcą w Dynamics 365 Supply Chain Management. Wyjaśniono również, jak skonfigurować przepływ pracy w celu zapewnienia nowych użytkowników współpracujących z dostawcami oraz jak zarządzać rolami zabezpieczeń dla tych użytkowników.

> [!NOTE]
> Informacje dotyczące konfiguracji ról zabezpieczeń dla współpracy z dostawcami dotyczą tylko bieżącej wersji Finance and Operations. W systemie Microsoft Dynamics AX 7.0 (luty 2016 r.) i aplikacji Microsoft Dynamics AX w wersji 7.0.1 (maj 2016 r.) do współpracy z dostawcami służy moduł **Portal dostawców**. Aby uzyskać informacje na temat uprawnień użytkowników portalu sprzedawcy w Microsoft Dynamics AX, patrz [Bezpieczeństwo użytkownika portalu sprzedawcy](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Konfigurowanie ról zabezpieczeń współpracy z dostawcami

Specjalista ds. zamówień lub sprzedawca, który ma wystarczające uprawnienia, może zażądać, aby osoba kontaktowa została udostępniona jako użytkownik, włączając opcję **Użytkownik sprzedawcy** w rekordzie osoby kontaktowej. Podczas procesu dostarczania uprawnień wybierane są uprawnienia użytkownika dla nowego użytkownika zewnętrznego, a następnie przesyłany jest wniosek o nowego użytkownika sprzedawcy. Bardzo ważne jest prawidłowe skonfigurowanie uprawnień użytkowników dostępnych do wyboru w wniosku użytkownika-dostawcy. W przeciwnym razie sprzedawcy mogą uzyskać dostęp do informacji, do których nie powinni mieć dostępu do Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Skonfiguruj role zabezpieczeń, które są dostępne do wyboru, gdy dla danej osoby kontaktowej zostanie użyte żądanie nowego użytkownika

1. Wybierz **Administracja systemu** &gt; **Bezpieczeństwo** &gt; **Role zewnętrzne**.
2. Wybierz opcję **Nowy**, a następnie wybierz rolę zabezpieczeń i rolę strony **Dostawca**.

Możesz dodać role **Administrator dostawcy (zewn.)** i **Dostawca (zewn.)**, dostępne w Supply Chain Management. Alternatywnie można użyć ról zabezpieczeń, które zostały utworzone przez firmę.

Rolę **Administrator dostawcy (zewn.)** należy udostępnić tylko wtedy, gdy sprzedawcy powinni mieć możliwość tworzenia nowych kontaktów, składania wniosków o nowych użytkowników i zmiany informacji o użytkownikach w ramach współpracy ze sprzedawcami oraz obsługi tych wniosków za pomocą przepływu pracy.

Jeśli planujesz ręcznie skonfigurować kontakty sprzedawców i użytkowników, możesz udostępnić tylko rolę **Dostawca (zewn.)**. Ta rola będzie jedyną rolą, o którą można się ubiegać za pomocą żądania użytkownika sprzedawcy.

> [!NOTE]
> Uwaga: Rola **SystemUser** jest przyznawana automatycznie podczas ręcznego tworzenia nowego konta użytkownika w systemie Dynamics . W związku z tym należy usunąć tę rolę i przypisać rolę **SystemExternalUser**. Jeśli nowe konta użytkowników są tworzone za pomocą przepływu pracy, który jest inicjowany przez żądanie dostarczenia nowego użytkownika przez sprzedawcę, przypisana zostanie jedna lub więcej ról, które zostały skonfigurowane dla współpracy sprzedawców oraz rola **SystemExternalUser**.

#### <a name="vendor-admin-external-security-role"></a>Rola bezpieczeństwa Administrator dostawcy (zewn.)

Rola **Administrator dostawcy (zewn.)** może być używana w przypadku zewnętrznych sprzedawców, którzy utrzymują informacje kontaktowe sprzedawców i składają wnioski o udostępnienie nowych użytkowników współpracujących ze sprzedawcami. Użytkownicy zewnętrzni posiadający tę rolę bezpieczeństwa mogą wykonywać następujące zadania:

- Wyświetlanie i modyfikowanie informacji o osobie kontaktowej, takich jak jej tytuł, adres e-mail i numer telefonu.
- Dodaj nową lub istniejącą osobę kontaktową do kont sprzedawców, dla których jest ona kontaktem.
- Usuń wszystkie utworzone przez siebie osoby kontaktowe.
- Aktywowanie lub dezaktywowanie powiązania między osobą kontaktową a kontem sprzedawcy. Po dezaktywacji powiązania między osobą kontaktową a kontem sprzedawcy nie będzie można powoływać się na tę osobę na nowych zamówieniach zakupu lub innych dokumentach.
- Odmówić lub zezwolić osobie kontaktowej na dostęp do dokumentów w interfejsie współpracy ze sprzedawcą, które są specyficzne dla konta sprzedawcy. Po dezaktywacji powiązania między osobą kontaktową a kontem sprzedawcy zawsze odmawia się dostępu do dokumentów, które są specyficzne dla tego konta sprzedawcy.
- Zażądaj utworzenia nowego konta użytkownika dla osoby kontaktowej za pomocą akcji **Zapewnij użytkownika**.
- Zażądaj dezaktywacji konta użytkownika osoby kontaktowej.
- Żądanie modyfikacji konta użytkownika osoby kontaktowej w celu dodania lub usunięcia ról zabezpieczeń.
- Wyświetlanie RFQ.

#### <a name="vendor-external-security-role"></a>Rola bezpieczeństwa Dostawca (zewn.)

Rola **Dostawca (zewn.)** może być używana dla dostawców zewnętrznych, którzy będą pracować z zamówieniami zakupu. Użytkownicy zewnętrzni posiadający tę rolę bezpieczeństwa mogą wykonywać następujące zadania:

- Odpowiadanie na zamówienia zakupu i wyświetlanie informacji o nich.
- Obsługa faktur w portalu współpracy z dostawcami.
- Wyświetl zapasy konsygnacyjne.
- Przeglądanie RFQ i odpowiadanie na nie.
- Wyświetlanie informacji o dostawcy.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Skonfiguruj role bezpieczeństwa, które są używane, gdy potencjalni sprzedawcy są wprowadzani na rynek

Aby włączyć do systemu sprzedawców, którzy zostali zainicjowani poprzez wniosek rejestracyjny potencjalnego sprzedawcy, należy skonfigurować zewnętrzną rolę bezpieczeństwa. Rola ta zostanie przypisana nowym użytkownikom w procesie konfiguracji, który jest sterowany przez przepływ typu **Przepływ żądań użytkowników (platforma)**. Więcej informacji na ten temat można znaleźć w punkcie [Ustawianie przepływów pracy w celu przetwarzania żądań użytkowników współpracujących z dostawcami](#set-up-workflows-to-process-vendor-collaboration-user-requests) w dalszej części tego tematu.

Aby uzyskać informacje na temat sposobu przyjmowania potencjalnych sprzedawców, patrz [Wprowadzanie sprzedawców](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Skonfiguruj rolę bezpieczeństwa, która jest używana podczas składania wniosku o nowego użytkownika potencjalnego sprzedawcy

1. Wybierz **Administracja systemu** > **Bezpieczeństwo** > **Role zewnętrzne**.
2. Wybierz opcję **Nowy**, a następnie wybierz rolę zabezpieczeń i rolę strony **Potencjalny dostawca**.

Należy dodać rolę **Potencjalny sprzedawca (zewn.)**, która jest podana w Supply Chain Management.

Rola bezpieczeństwa umożliwi dostęp tylko do kreatora rejestracji nowego sprzedawcy.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Konfigurowanie przepływów pracy w celu przetwarzania wniosków użytkowników o współpracę z dostawcami

Aby zagwarantować, że wszystkie istotne zadania zostaną wykonane oraz że zostaną wydane odpowiednie zatwierdzenia, należy skonfigurować przepływy pracy do obsługi wniosków użytkowników współpracujących z dostawcami.

Wnioski użytkowników współpracujących z dostawcami są składane przez dostawców zewnętrznych, którzy mają rolę bezpieczeństwa **Administrator dostawcy (zewn.)** lub podobne uprawnienia, lub przez specjalistów ds. zakupów w Twojej firmie. Mogą być one również generowane na podstawie wniosków o rejestrację potencjalnych sprzedawców podczas procesu ich przyjmowania.

Istnieją trzy typy wniosków:

- Żądanie udostępnienia nowego użytkownika
- Prośby o dezaktywację istniejącego użytkownika
- Prośby o zmianę ról zabezpieczeń istniejącego użytkownika

Aby uzyskać więcej informacji na temat żądań użytkowników współpracujących z dostawcami, patrz [Zarządzanie użytkownikami współpracującymi z dostawcami](manage-vendor-collaboration-users.md).

Należy utworzyć dwa lub więcej przepływów pracy, aby przetworzyć wszystkie trzy typy żądań użytkowników współpracujących z dostawcami. Nowe przepływy pracy tworzy się na stronie **Przepływy pracy użytkownika**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Przykład przepływu pracy dla nadawania uprawnień nowym użytkownikom i modyfikacji ról zabezpieczeń

Aby obsłużyć żądania użytkowników sprzedawcy dotyczące tworzenia nowych użytkowników i modyfikowania ról zabezpieczeń, można na początku przepływu umieścić warunek rozgałęzienia. W ten sposób wykorzystywana jest inna gałąź przepływu pracy, w zależności od tego, czy żądanie dotyczy utworzenia nowego użytkownika, czy też modyfikacji istniejącego.

Aby skonfigurować to rozgałęzienie, należy utworzyć nowy przepływ pracy typu **Przepływ żądań użytkownika (platforma)**. Gałęzie tego przepływu pracy mogą zawierać następujące elementy.

#### <a name="branch-to-provision-new-users"></a>Oddział do zaopatrywania nowych użytkowników

1. Przypisz zadanie zatwierdzania do osoby, która jest odpowiedzialna za zatwierdzanie, że nowi użytkownicy powinni mieć dostęp do informacji o współpracy z dostawcami.
2. Przydziel zadanie osobie, która jest odpowiedzialna za zgłaszanie zapotrzebowania na nowe konta użytkowników Microsoft Azure Active Directory (Azure AD) w portalu Azure. W tym kroku należy użyć predefiniowanego zadania **Wyślij zaproszenie użytkownika Azure B2B**. Użytkownicy B2B mogą być automatycznie eksportowani do Azure AD. Użyj predefiniowanej **Konfiguracji Azure AD użytkownika B2B**. Aby uzyskać więcej informacji, zobacz [Eksport użytkowników B2B do Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Przypisz zadanie zatwierdzenia do osoby, która przesyła dane do Azure. Jeśli konto nie zostanie pomyślnie utworzone, osoba ta odrzuca zadanie i kończy przepływ pracy. To zadanie zatwierdzania można pominąć, jeśli włączono krok, który automatycznie eksportuje nowe konta użytkowników do Azure za pomocą interfejsu programowania aplikacji B2B (API).
4. Dodaj zautomatyzowane zadanie, które zapisuje nowego użytkownika. W tym kroku należy użyć predefiniowanego zadania **Zautomatyzowane udostępnianie użytkownika**.
5. Dodaj zadanie, które powiadomi nowego użytkownika. Możesz wysłać nowemu użytkownikowi powitalną wiadomość e-mail, która zawiera adres URL do Supply Chain Management. Ta wiadomość e-mail może wykorzystywać szablon utworzony na stronie **Wiadomości e-mail**, a następnie wybrany na stronie **Parametry przepływu pracy użytkownika**. Szablon może zawierać tag **%portalURL%**. Kiedy zostanie wygenerowana wiadomość powitalna, ten znacznik, który zostanie zastąpiony przez adres URL lokatora Supply Chain Management.

    > [!NOTE]
    > Ten przepływ pracy może być wykorzystany w wielu scenariuszach, w których użytkownik jest wprowadzany do systemu. Na przykład, można go użyć, gdy potencjalni sprzedawcy lub osoby kontaktowe wymagają konta współpracy ze sprzedawcami. Dlatego powinieneś sformułować e-mail jako ogólne stwierdzenie, które może być wykorzystane do wielu celów.

#### <a name="branch-to-modify-security-roles"></a>Oddział umożliwiający modyfikację ról zabezpieczeń

1. Przypisać zadanie zatwierdzania do osoby, która jest odpowiedzialna za zatwierdzanie zmian w rolach zabezpieczeń.
2. Dodaj automatyczne zadanie, które dodaje lub usuwa odpowiednie role zabezpieczeń. W tym kroku należy użyć zadania **Zautomatyzowane udostępnianie użytkownika**.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Przykład przepływu pracy dla dezaktywacji użytkownika

Należy utworzyć przepływ typu **Inaktywacja platformy przepływu żądań użytkowników**, a następnie dodać do niego następujące zadania.

1. Przypisać zadanie zatwierdzania do osoby, która jest odpowiedzialna za akceptowanie wniosków o dezaktywację użytkowników. Możesz dodać warunki, aby zautomatyzować ten etap zatwierdzania.
2. Dodaj zautomatyzowane zadanie, które dezaktywuje użytkownika. W tym kroku należy użyć zadania **Zautomatyzowana dezaktywacja użytkowników**.
3. Dodaj wszelkie zadania związane z czyszczeniem, które są wymagane. Na przykład, można dodać zadanie, które usuwa konto z katalogu w portalu Azure.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Umożliwienie współpracy z dostawcami dla określonego dostawcy

Przed utworzeniem konta użytkownika dla osoby, która będzie korzystać ze współpracy z dostawcami, należy skonfigurować dostawcę w taki sposób, aby mógł on korzystać ze współpracy z dostawcami. Na stronie **Dostawcy** na karcie **Ogólne** ustaw pole **Aktywacja współpracy**. Dostępne są następujące opcje:

- **Aktywne (zamówienie jest automatycznie potwierdzane)** – zamówienia są automatycznie potwierdzane, jeśli sprzedawca zaakceptuje je bez żądania zmian.
- **Aktywna (zamówienie zakupu nie zostało automatycznie potwierdzone)** — Twoja organizacja musi ręcznie potwierdzać zamówienia zakupu po ich zaakceptowaniu przez sprzedawcę.

> [!NOTE]
> Specjaliści ds. zakupów w Twojej firmie również mogą wykonać to zadanie.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Rozwiązywanie problemów związanych z konfigurowaniem nowych użytkowników współpracy z dostawcami

Nowi użytkownicy współpracujący z dostawcami są dostarczani za pomocą przepływu pracy, który został skonfigurowany do przetwarzania żądań użytkowników współpracujących z dostawcami o typie **Udostępnianie użytkownika sprzedawcy**.

Jeśli adres e-mail nowego użytkownika współpracującego z dostawcą należy do domeny, która jest zarejestrowana w Azure jako dzierżawa (czyli jeśli jest to konto domeny zarządzanej), adres e-mail musi być istniejącym kontem Azure AD. W przeciwnym razie nie można ukończyć procesu tworzenia i obsługi.

Więcej informacji o procesie, który jest wykorzystywany w zadaniu **Wyślij zaproszenie użytkownika Azure B2B** w przepływie dla zarządzania kontem Azure AD, patrz [Azure Active Directory – współpraca B2B](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Współpraca z dostawcami zewnętrznymi przy użyciu modułu Współpraca z dostawcami](vendor-collaboration-work-external-vendors.md)

Obejrzyj krótki film o procesie dołączania dostawców: [Dołączanie nowego dostawcy](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
