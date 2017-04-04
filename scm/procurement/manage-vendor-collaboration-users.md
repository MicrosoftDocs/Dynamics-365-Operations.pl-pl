---
title: "Zarządzanie użytkownikami portalu współpracy z dostawcami"
description: "W tym temacie opisano sposoby wnioskowania o zainicjowanie obsługi nowych użytkowników i dodawania nowych osób kontaktowych w portalu współpracy z dostawcami."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 380f1bcdf7109dc12fd898199033eac7710d863c
ms.lasthandoff: 03/31/2017


---

# <a name="manage-vendor-collaboration-users"></a>Zarządzanie użytkownikami portalu współpracy z dostawcami

W tym temacie opisano sposoby wnioskowania o zainicjowanie obsługi nowych użytkowników i dodawania nowych osób kontaktowych w portalu współpracy z dostawcami. 

Interfejs współpracy z dostawcami w programie Microsoft Dynamics 365 for Operations udostępnia dostawcom zewnętrznym informacje o zamówieniach zakupu, fakturach i zapasach konsygnacyjnych. Można tworzyć nowe osoby kontaktowe w portalu współpracy z dostawcami i wnioskować o zainicjowanie obsługi nowych użytkowników, jeżeli pracujesz jako zewnętrzny dostawca z rolą zabezpieczeń **Administrator dostawcy (zewnętrzny)** lub podobnymi uprawnieniami. Te zadania można również wykonać podczas pracy jako pracownik działu zaopatrzenia. W tym temacie ta rola odnosi się do pracownika działu zaopatrzenia, który pracuje w firmie będącej właścicielem wystąpienia programu Dynamics 365 for Operations. Aby uzyskać więcej informacji na temat sposobu używania dostawcy współpracy w przypadku zewnętrznego dostawcy, zobacz [dostawcy z klientami](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Aby uzyskać więcej informacji na temat sposobu używania dostawcy współpracy w przypadku zamówień zawodowych, zobacz [dostawcy współpracy z innymi firmami,](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Dodawanie nowych osób kontaktowych w portalu współpracy z dostawcami
Jeśli ktoś ma mieć dostęp do portalu współpracy z dostawcami, musi najpierw zostać dodany jako osoba kontaktowa w portalu współpracy z dostawcami. Można również jako osoby kontaktowe dodać pracowników firmy, którzy nie będą używać portalu współpracy z dostawcami. Na przykład mogą być osobami kontaktowymi w sprawie innych rodzajów informacji zaopatrzeniowych. Nowe kontakty są dodawane w **wszystkie kontakty** strona, która jest dostępna z **współpracy Dostawca**&gt;**kontakty** menu. Aby dodać nową osobę kontaktową:

1.  Kliknij przycisk **Nowy**.
2.  Wprowadź szczegóły osoby kontaktowej.
3.  Wybierz firmę, którą ta osoba reprezentuje w Twojej organizacji, oraz firmę, z którą będzie współpracować w drugiej organizacji. Można to zrobić przez zaznaczenie **osoby prawnej w mojej firmie**/**podmiotu prawnego w firmie nabywcy, do** para.
4.  Kliknij przycisk **Utwórz**.

Jeśli chcesz usunąć osobę kontaktową, możesz wykasować tylko osoby utworzone przez siebie.

## <a name="vendor-collaboration-user-requests"></a>Żądania użytkowników portalu współpracy z dostawcami
Wnioski o dodanie użytkowników do portalu współpracy z dostawcami mogą zgłaszać pracownicy działu zaopatrzenia i administratorzy zewnętrznych dostawców.

-   W przypadku zewnętrznego dostawcy, możesz przesłać żądania od **wszystkie kontakty** strony w obrębie **współpracy Dostawca** modułu.
-   Pracownik działu zaopatrzenia przesyła wnioski ze strony **Wyświetl osoby kontaktowe**. Aby to zrobić, na rekordu dostawcy w **instalacji** sekcji w okienku akcji wybierz opcję **kontakty**&gt;**wyświetlić kontakty**.

Można złożyć wniosek o zainicjowanie obsługi użytkownika, dezaktywację użytkownika lub modyfikację ról zabezpieczeń. Jeśli jesteś administratorem zewnętrznych dostawców, musisz być zarejestrowany jako osoba kontaktowa dla dostawców, o których użytkowników chcesz składać wnioski, oraz mieć dostęp do interfejsu współpracy z dostawcami dla tych dostawców.  

Przesłany wniosek jest dodawany do listy **Żądania użytkowników portalu współpracy z dostawcami** w module **Portal współpracy z dostawcami** oraz do listy **Żądanie użytkownika portalu współpracy z dostawcami** w module **Zaopatrzenie i sourcing** (moduł Zaopatrzenie i sourcing nie jest dostępny dla użytkowników zewnętrznych).

### <a name="provision-a-user"></a>Inicjowanie obsługi użytkownika

Zanim będzie można wnioskować o zainicjowanie obsługi nowego użytkownika, ta osoba musi być skonfigurowana jako osoba kontaktowa dla jednego lub więcej dostawców. Aby utworzyć wniosek o nowego użytkownika portalu współpracy z dostawcami:

1.  Na **wszystkie kontakty** kliknij przycisk **użytkownika dostawcy przepis**.
2.  Wprowadź adres e-mail użytkownika. Ten adres będzie wykorzystywany przez użytkownika do logowania się do programu Dynamics 365 for Operations. Jeśli adres e-mail należy do domeny zarejestrowanej jako dzierżawca w usłudze Microsoft Azure, musi być adresem istniejącego konta w usłudze Azure Active Directory (AAD), aby proces inicjowania obsługi został pomyślnie wykonany. Jeśli adres e-mail nie należy do domeny zarejestrowanej w usłudze Microsoft Azure, konto usługi AAD zostanie utworzone jako część procesu inicjowania obsługi i nowy użytkownik otrzyma wiadomość e-mail z zaproszeniem. Adresy z domen, takich jak e-mail konsumenta @hotmail.com, @gmail.com, lub @comcast.netnie może służyć do rejestrowania 365 Dynamics dla działań użytkownika.
3.  W opcji **Dostęp do portalu współpracy z dostawcami jest dozwolony** ustaw wartość **Tak** dla wszystkich firm, do których użytkownik musi mieć dostęp.
4.  W sekcji **Przypisz role użytkownika** zaznacz pole wyboru **Przypisz** dla ról zabezpieczeń, które powinien mieć nowy użytkownik.
5.  Kliknij przycisk **Prześlij**.

Po przesłaniu żądania użytkownika dostawcy **dostawcy współpracy dostęp dozwolony** pole jest ustawione na **tak** dla konta wybranego dostawcy i użytkownika żądać przepływ pracy jest uruchamiany. W ramach przepływu pracy nowy użytkownik jest tworzony w programie Dynamics 365 for Operations i są mu przypisywane role zabezpieczeń. Ponadto jest aktywowana usługa Azure B2B, która inicjuje interakcję z portalem Azure i kojarzy nowe lub istniejące konto w usłudze AAD z kontem użytkownika w programie Dynamics 365 for Operations.

### <a name="inactivate-a-user"></a>Dezaktywowanie użytkownika

Istnieją dwa sposoby usuwania użytkownikowi dostępu do portalu współpracy z dostawcami:

-   Na stronie **Kontakty** dla dostawcy w opcji **Dostęp do portalu współpracy z dostawcami jest dozwolony** ustaw wartość **Nie** dla osoby kontaktowej. Można to zrobić osobno dla każdej firmy, w której użytkownik jest osobą kontaktową. Tej opcji mogą używać tylko pracownicy działu zaopatrzenia.
-   Zdezaktywuj całe konto użytkownika, przesyłając wniosek **Dezaktywuj użytkownika-dostawcę**.

Aby zażądać inaktywowanych użytkownika:

1.  Na **wszystkie kontakty** kliknij przycisk **Dezaktywuj****użytkownika dostawcy**.
2.  Wpisz komentarz w polu **Uzasadnienie biznesowe**.
3.  Kliknij przycisk **Prześlij**.

### <a name="modify-security-roles"></a>Modyfikowanie ról zabezpieczeń

**Obsługa ról użytkownika dostawcy** strona jest taka sama, jak **użytkownika dostawcy przepis** strona chyba, że można edytować listę ról zabezpieczeń.  

Na żądanie, że role zabezpieczeń zostaną zmienione dla użytkownika:

1.  Na **wszystkie kontakty** kliknij przycisk **Zachowaj****ról użytkownika dostawcy**.
2.  Wpisz komentarz w polu **Uzasadnienie biznesowe**.
3.  W sekcji **Obsługa ról użytkowników** wybierz role zabezpieczeń, które chcesz przypisać, a wyczyść te, które mają zostać usunięte.
4.  Click **Submit**.



