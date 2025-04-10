# 📘 Metodología de Nomenclatura de Test Cases para Frontend y Backend

## 1. Introducción

El objetivo estandarizar la nomenclatura de los **Test Cases** en proyectos que incluyan desarrollo **frontend** y **backend**, donde se pueda garantizar claridad, consistencia y facilidad en la rotación de roles. Se basa en buenas prácticas reconocidas incluyendo normas como **ISTQB**, **IEEE 829**.


## 2. Estándares y Normativas Consultadas

- **ISTQB (International Software Testing Qualifications Board)**: Buenas prácticas para la redacción de Test Cases.
- **IEEE 829 (Standard for Software and System Test Documentation)**: Estructura y contenido recomendado para la documentación de pruebas.
## 3. Convención de Nombres para Test Cases

### 3.1. Estructura General del Nombre

[PREFIJO][MÓDULO][CONDICIÓN/ACCIÓN]_[RESULTADO ESPERADO]

### 3.2. Reglas Generales

- Usar mayúsculas con guiones bajos (`test_case`) para separar elementos.
- El nombre debe ser conciso pero descriptivo.
- Utilizar palabras clave que permitan identificar el propósito del test case.
- Evitar abreviaturas ambiguas.
- Siempre incluir un **identificador único**, como un ID secuencial o UUID si se usa herramienta de gestión.

---

## 4. Prefijos para Diferenciación

| Prefijo | Tipo de Prueba   | Descripción                                     |
|---------|------------------|-------------------------------------------------|
| `FE_`   | Frontend          | Pruebas de UI, componentes, interacciones       |
| `BE_`   | Backend           | Lógica de negocio, procesos internos            |
| `API_`  | API REST/SOAP     | Pruebas de endpoints                            |
| `E2E_`  | End-to-End        | Flujo completo entre FE y BE                    |
| `UT_`   | Unit Test         | Pruebas unitarias                               |
| `INT_`  | Integration       | Pruebas de integración entre servicios          |

---

## 5. Ejemplos Prácticos
### 5.1. Frontend

- `FE_LoginPage_EmptyUsernameAndPassword_ShowsRequiredErrors`
- `FE_SignupForm_ValidInput_EnablesSubmitButton`
- `FE_Navbar_ClickLogo_RedirectsToHomePage`
- `FE_SearchInput_EnterKeyword_DisplaysSearchResults`
- `FE_ProfilePage_EditMode_SaveChanges_UpdatesUI`

### 5.2. Backend

- `BE_AuthService_ValidCredentials_ReturnsJWTToken`
- `BE_UserService_GetUserById_UserExists_ReturnsUserObject`
- `BE_OrderService_CancelPaidOrder_ReturnsError`
- `BE_InventoryService_DecreaseStock_WhenOrderPlaced_UpdatesQuantity`
- `BE_PaymentService_ProcessPayment_InvalidCard_ReturnsFailure`

### 5.3. API

- `API_POST_Login_WithCorrectCredentials_Returns200AndToken`
- `API_GET_Products_WithCategoryFilter_ReturnsFilteredResults`
- `API_PUT_UpdateUserProfile_WithInvalidEmail_Returns400`
- `API_DELETE_DeleteAccount_WhenAuthenticated_Returns204`
- `API_GET_Orders_WithNoAuth_Returns401Unauthorized`

### 5.4. E2E (End-to-End)

- `E2E_UserLogin_AndCheckoutFlow_EndsInOrderConfirmation`
- `E2E_Visitor_RegistersAccount_AndReceivesConfirmationEmail`
- `E2E_User_AddsProductToCart_ThenRemovesIt_CartIsEmpty`
- `E2E_AdminLogsIn_AndCreatesNewProduct_ProductVisibleInStore`
- `E2E_UserRequestsPasswordReset_EmailIsSent_ResetLinkWorks`


---

## 6. Casos de Uso y Excepciones


Estas excepciones ayudan a:

- Clasificar los Test Cases según su **prioridad o estabilidad**.
- **Facilitar el mantenimiento** y la planificación de regresiones.
- **Distinguir pruebas automatizadas** de las que requieren intervención manual.

| Caso Especial               | Recomendación                          | Ejemplo                                                                 |
|----------------------------|----------------------------------------|-------------------------------------------------------------------------|
| Pruebas de regresión        | Añadir sufijo `_Regression`            | `FE_Login_ValidCredentials_ReturnsDashboard_Regression`                |
| Pruebas críticas de negocio | Añadir sufijo `_Critical`              | `API_POST_PaymentWithValidCard_ReturnsSuccess_Critical`                |
| Pruebas temporales/manuales | Incluir `_TEMP` o `_MANUAL` al final   | `BE_UserService_UpdateUserRole_TEMP`<br>`E2E_DeleteAccount_MANUAL`     |
| Automatización de pruebas   | Usar sufijo `_Auto`                    | `FE_Cart_AddProduct_ShowsInCart_Auto`                                  |

---

## 7. Herramientas Recomendadas para Validar Nombres

### 7.1. Linters o Validadores Personalizados

- **ESLint / Custom Test Case Name Rules** (para JavaScript/TypeScript)
- **Pre-commit Hooks** usando herramientas como Husky
- Validaciones en pipelines CI/CD para evitar test con nombres inválidos

### 7.2. Test Management Tools

- **TestRail**: Permite definir plantillas de nombre y filtros.
- **Zephyr for Jira**: Compatible con validaciones personalizadas.
- **Xray**: Integra criterios de aceptación y etiquetas que permiten organización por tipo.

---

## 8. Referencias

### Normativas y Documentos Técnicos

- [ISTQB Foundation Level Syllabus](https://www.istqb.org/)
- [IEEE 829 - Standard for Software Test Documentation](https://ieeexplore.ieee.org/search/searchresult.jsp?newsearch=true&contentType=books&queryText=test)
- [Google Testing Blog](https://testing.googleblog.com)

### Recursos de Buenas Prácticas

- [Test Naming Best Practices](https://medium.com/@kshitijsharma94/best-practices-for-writing-effective-test-cases-c2628cce59b8)
- [Naming Conventions for Unit Tests – Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices)

### Herramientas

- [TestRail](https://www.gurock.com/testrail/)
- [Xray Test Management for Jira](https://www.getxray.app/)
- [Zephyr for Jira](https://marketplace.atlassian.com/apps/1213259/zephyr-scale-test-management)

