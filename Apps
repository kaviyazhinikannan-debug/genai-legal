import streamlit as st

st.set_page_config(page_title="GenAI Legal Assistant")

st.title("GenAI Legal Assistant 🧠⚖️")
st.write("Upload a contract and understand risks in simple language.")

uploaded_file = st.file_uploader(
    "Upload Contract (PDF / TXT)",
    type=["pdf", "txt"]
)

if uploaded_file:
    if uploaded_file.type == "text/plain":
        contract_text = uploaded_file.read().decode("utf-8")
        st.subheader("Contract Text")
        st.text_area("Uploaded Contract", contract_text, height=300)

        st.subheader("Risk Detection")
        text = contract_text.lower()

        if "penalty" in text:
            st.error("⚠️ Penalty clause detected")
        if "termination" in text:
            st.warning("⚠️ Termination condition found")
        if "indemnity" in text:
            st.warning("⚠️ Indemnity clause found")

        st.subheader("Simple Summary")
        st.write("This contract includes obligations, termination rules and possible penalties.")
    else:
        st.info("PDF support coming soon 🚧")
