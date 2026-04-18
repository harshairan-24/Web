import mysql.connector

# Logic to connect to your MySQL
def load_data():
    conn = mysql.connector.connect(host="localhost", user="root", password="yourpassword", database="school")
    query = "SELECT * FROM students"
    return pd.read_sql(query, conn)

df = load_data()
st.table(df)