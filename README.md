# アプリの動作例
[![Image from Gyazo](https://i.gyazo.com/9d29ebcc8146522f6bb465d41be39b70.gif)](https://gyazo.com/9d29ebcc8146522f6bb465d41be39b70)

```tsx
//App.tsx
.
.
.
export default function App() {
  const [userProfiles, setUserProfiles] = useState<Array<UserProfile>>([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(false);
  
   const onClickFetchUser = () => {
    setLoading(true);
    setError(false);
.
.
.
return (
    <div className="App">
      <button onClick={onClickFetchUser}>データ取得</button>
      <br />
      {error ? (
        <p　style={{color: "red"}}>データの取得に失敗しました</p>
      ) : loading ? (
        <p>Loading...</p>
      ) : (
        <>
        {userProfiles.map((user) => (
        <UserCard key={user.id} user={user} />
        ))}
        </>
      )}
    </div>
  );
}
  
```
