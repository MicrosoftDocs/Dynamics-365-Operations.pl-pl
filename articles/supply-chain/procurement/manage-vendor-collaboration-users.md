---
title: Zarządzanie użytkownikami portalu współpracy z dostawcami
description: W tym temacie opisano sposoby wnioskowania o zainicjowanie obsługi nowych użytkowników i dodawania nowych osób kontaktowych w portalu współpracy z dostawcami.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ff0d11bf2c42f7ae63e3db5f31f3ffea2c28f693
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578135"
---
# <a name="manage-vendor-collaboration-users"></a>Zarządzanie użytkownikami portalu współpracy z dostawcami

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposoby wnioskowania o zainicjowanie obsługi nowych użytkowników i dodawania nowych osób kontaktowych w portalu współpracy z dostawcami. 

Interfejs współpracy z dostawcami w Dynamics 365 Supply Chain Management udostępnia dostawcom zewnętrznym informacje o zamówieniach zakupu, fakturach i zapasach konsygnacyjnych. Można tworzyć nowe osoby kontaktowe w portalu współpracy z dostawcami i wnioskować o zainicjowanie obsługi nowych użytkowników, jeżeli pracujesz jako zewnętrzny dostawca z rolą zabezpieczeń **Administrator dostawcy (zewnętrzny)** lub podobnymi uprawnieniami. Te zadania można również wykonać podczas pracy jako pracownik działu zaopatrzenia. W tym temacie ta rola odnosi się do pracownika działu zaopatrzenia, który pracuje w firmie będącej właścicielem wystąpienia Supply Chain Management. Aby uzyskać więcej informacji na temat używania portalu współpracy z dostawcami przez zewnętrznego dostawcę, zobacz [Współpraca z odbiorcami przy użyciu modułu Współpraca z dostawcami](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Aby uzyskać więcej informacji na temat używania portalu współpracy z dostawcami przez pracownika działu zaopatrzenia, zobacz [Współpraca z zewnętrznymi dostawcami](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Dodawanie nowych osób kontaktowych w portalu współpracy z dostawcami
Jeśli ktoś ma mieć dostęp do portalu współpracy z dostawcami, musi najpierw zostać dodany jako osoba kontaktowa w portalu współpracy z dostawcami. Można również jako osoby kontaktowe dodać pracowników firmy, którzy nie będą używać portalu współpracy z dostawcami. Na przykład mogą być osobami kontaktowymi w sprawie innych rodzajów informacji zaopatrzeniowych. Nowe osoby kontaktowe są dodawane na stronie **Wszystkie osoby kontaktowe**, do której można przejść z menu **Portal współpracy z dostawcami** &gt; **Kontakty**. Aby dodać nową osobę kontaktową:

1.  Kliknij przycisk **Nowy**.
2.  Wprowadź szczegóły osoby kontaktowej.
3.  Wybierz firmę, którą ta osoba reprezentuje w Twojej organizacji, oraz firmę, z którą będzie współpracować w drugiej organizacji. W tym celu zaznacz wartości w parze pól **Podmiot prawny w mojej firmie**/**Podmiot prawny w firmie odbiorcy**.
4.  Kliknij przycisk **Utwórz**.

Jeśli chcesz usunąć osobę kontaktową, możesz wykasować tylko osoby utworzone przez siebie.

## <a name="vendor-collaboration-user-requests"></a>Żądania użytkowników portalu współpracy z dostawcami
Wnioski o dodanie użytkowników do portalu współpracy z dostawcami mogą zgłaszać pracownicy działu zaopatrzenia i administratorzy zewnętrznych dostawców.

-   Zewnętrzny dostawca przesyła wnioski ze strony **Wszystkie osoby kontaktowe** w module **Portal współpracy z dostawcami**.
-   Pracownik działu zaopatrzenia przesyła wnioski ze strony **Wyświetl osoby kontaktowe**. W tym celu w rekordzie dostawcy w sekcji **Ustawienia** w okienku akcji wybierz kolejno opcje **Kontakty** &gt; **Wyświetl osoby kontaktowe**.

Można złożyć wniosek o zainicjowanie obsługi użytkownika, dezaktywację użytkownika lub modyfikację ról zabezpieczeń. Jeśli jesteś administratorem zewnętrznych dostawców, musisz być zarejestrowany jako osoba kontaktowa dla dostawców, o których użytkowników chcesz składać wnioski, oraz mieć dostęp do interfejsu współpracy z dostawcami dla tych dostawców.  

Przesłany wniosek jest dodawany do listy **Żądania użytkowników portalu współpracy z dostawcami** w module **Portal współpracy z dostawcami** oraz do listy **Żądanie użytkownika portalu współpracy z dostawcami** w module **Zaopatrzenie i sourcing** (moduł Zaopatrzenie i sourcing nie jest dostępny dla użytkowników zewnętrznych).

### <a name="provision-a-user"></a>Inicjowanie obsługi użytkownika

Zanim będzie można wnioskować o zainicjowanie obsługi nowego użytkownika, ta osoba musi być skonfigurowana jako osoba kontaktowa dla jednego lub więcej dostawców. Aby utworzyć wniosek o nowego użytkownika portalu współpracy z dostawcami:

1. Na stronie **Wszystkie osoby kontaktowe** kliknij opcję **Inicjuj obsługę użytkownika-dostawcy**.
2. Wprowadź adres e-mail użytkownika. Ten adres będzie używany przez użytkownika do logowania się w Supply Chain Management. Jeśli adres e-mail należy do domeny zarejestrowanej jako dzierżawca w usłudze Microsoft Azure, musi być adresem istniejącego konta w usłudze Azure Active Directory (AAD), aby proces inicjowania obsługi został pomyślnie wykonany. Jeśli adres e-mail nie należy do domeny zarejestrowanej w usłudze Microsoft Azure, konto usługi AAD zostanie utworzone jako część procesu inicjowania obsługi i nowy użytkownik otrzyma wiadomość e-mail z zaproszeniem. Konsumenckie adresy e-mail, w domenach takich jak @hotmail.com, @gmail.com lub @comcast.net, nie mogą być używane do rejestrowania użytkowników.
3. W opcji **Dostęp do portalu współpracy z dostawcami jest dozwolony** ustaw wartość **Tak** dla wszystkich firm, do których użytkownik musi mieć dostęp.
4. W sekcji **Przypisz role użytkownika** zaznacz pole wyboru **Przypisz** dla ról zabezpieczeń, które powinien mieć nowy użytkownik.
5. Kliknij przycisk **Prześlij**.

Po przesłaniu wniosku o użytkownika dostawcy pole **Dostęp do portalu współpracy z dostawcami jest dozwolony** otrzymuje wartość **Tak** dla wybranego konta dostawcy i rozpoczyna się przepływ pracy wnioskowania o użytkownika. W ramach przepływu pracy nowy użytkownik jest tworzony i są mu przypisywane role zabezpieczeń. Ponadto jest aktywowana usługa Azure B2B, która inicjuje interakcję z portalem Azure i kojarzy nowe lub istniejące konto w usłudze AAD z kontem użytkownika w rozwiązaniu Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Na czym polega współpraca w usłudze Azure AD B2B?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

### <a name="inactivate-a-user"></a>Dezaktywowanie użytkownika

Istnieją dwa sposoby usuwania użytkownikowi dostępu do portalu współpracy z dostawcami:

-   Na stronie **Kontakty** dla dostawcy w opcji **Dostęp do portalu współpracy z dostawcami jest dozwolony** ustaw wartość **Nie** dla osoby kontaktowej. Można to zrobić osobno dla każdej firmy, w której użytkownik jest osobą kontaktową. Tej opcji mogą używać tylko pracownicy działu zaopatrzenia.
-   Zdezaktywuj całe konto użytkownika, przesyłając wniosek **Dezaktywuj użytkownika-dostawcę**.

Aby poprosić o dezaktywację użytkownika:

1.  Na stronie **Wszystkie osoby kontaktowe** kliknij opcję **Dezaktywuj** **użytkownika-dostawcę**.
2.  Wpisz komentarz w polu **Uzasadnienie biznesowe**.
3.  Kliknij przycisk **Prześlij**.

### <a name="modify-security-roles"></a>Modyfikowanie ról zabezpieczeń

Strona **Obsługa ról użytkowników-dostawców** jest taka sama, jak strona **Inicjuj obsługę użytkownika-dostawcy**, a różnica polega na tym, że można edytować listę ról zabezpieczeń.  

Aby poprosić o modyfikację ról zabezpieczeń dla użytkownika:

1.  Na stronie **Wszystkie osoby kontaktowe** kliknij opcję **Obsługa** **ról użytkowników-dostawców**.
2.  Wpisz komentarz w polu **Uzasadnienie biznesowe**.
3.  W sekcji **Obsługa ról użytkowników** wybierz role zabezpieczeń, które chcesz przypisać, a wyczyść te, które mają zostać usunięte.
4.  Kliknij przycisk **Prześlij**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]